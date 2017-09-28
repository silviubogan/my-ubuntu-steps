Title, launcher and indicator bars dissapeared after installing updates just before upgrading to Ubuntu 15.10 only on my user account (in the Guest session, there was no problem).

I wanted to upgrade my Ubuntu 15.04 to Ubuntu 15.10 but first I had to install the available updates. I installed all of them, then I was asked to reboot. I restarted the computer and I saw that there were no window decorations, no launcher bar and no indicator bar. I tried to open the software center from the terminal using the following command to disable the used graphics driver in the Additional drivers tab but it gives me the following errors.

silviu@silviu-desktop:~/Desktop$ sudo software-center
[sudo] password for silviu: 
2015-10-25 21:17:47,915 - softwarecenter.ui.gtk3.app - INFO - setting up proxy 'None'
Traceback (most recent call last):
  File "/usr/bin/software-center", line 130, in <module>
    app = SoftwareCenterAppGtk3(options, args)
  File "/usr/share/software-center/softwarecenter/ui/gtk3/app.py", line 338, in __init__
    self.icons)
  File "/usr/share/software-center/softwarecenter/ui/gtk3/session/appmanager.py", line 66, in __init__
    self.oauth_token = helper.find_oauth_token_sync()
  File "/usr/share/software-center/softwarecenter/backend/ubuntusso.py", line 141, in find_oauth_token_sync
    sso.find_credentials()
  File "/usr/share/software-center/softwarecenter/backend/login_impl/login_sso.py", line 74, in find_credentials
    self.proxy.find_credentials(self.appname, self._get_params())
  File "/usr/lib/python2.7/dist-packages/dbus/proxies.py", line 70, in __call__
    return self._proxy_method(*args, **keywords)
  File "/usr/lib/python2.7/dist-packages/dbus/proxies.py", line 145, in __call__
    **keywords)
  File "/usr/lib/python2.7/dist-packages/dbus/connection.py", line 651, in call_blocking
    message, timeout)
dbus.exceptions.DBusException: org.freedesktop.DBus.Error.NoReply: Did not receive a reply. Possible causes include: the remote application did not send a reply, the message bus security policy blocked the reply, the reply timeout expired, or the network connection was broken.
silviu@silviu-desktop:~/Desktop$ 

after a restart, I could start the Ubuntu Software Center, and by running it with sudo, it showed its menu bar so I could open Software Sources and select Additional drivers tab. I tried switching to the Nouveau driver and back again to the proprietary NVIDIA binary driver - version 340.93 from nvidia-340-updates and I still have the problem: no UI excepting the desktop - its icons and its context menu.


I tried running this command, but after the latest line written to terminal, I waited two minutes and it did nothing, just like it was blocked.

silviu@silviu-desktop:~/Desktop$ sudo /usr/bin/compiz-decorator --replace
Couldn't find a perfect decorator match; trying all decorators
Starting gtk-window-decorator



I also tried with ccsm to enable the window decorations, which in the CCSM window were set to disabled, but without success. The window decoration command is set to /usr/bin/gtk-window-decorator.




I see that the entire Unity application does not work: pressing Ctrl+Alt+T should start the terminal but it does nothing. I can open the terminal by right clicking the desktop (which correctly shows its icons) and selecting `Open in terminal`. The key combination `Alt+F2` does not work.

If I log in as Guest session, everything works well, the launcher, the indicator bar and the window decorations appear correctly.

I tried this: http://askubuntu.com/a/476623/29733 but it did not solve the problem.


I solved the problem using this: http://askubuntu.com/a/76951/29733
