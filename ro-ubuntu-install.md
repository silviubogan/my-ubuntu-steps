- Instalează actualizări.

- http://ubuntuhandbook.org/index.php/2014/10/enable-hibernate-option-in-ubuntu-14-10-unity/

- Instalează Dropbox de pe site-ul web oficial (adaugă depozitul Apt pentru actualizări).
	- Pentru a reporni Nautilus, managerul de fișiere: http://askubuntu.com/questions/19979/how-to-restart-nautilus-without-logging-out
	- Dropbox Preferences > Bandwidth > Upload rate > Don't limit.

- Firefox:
	- Configurează Firefox Sync (cheia de sincronizare este în Dropbox).
	- După prima sincronizare, repornește navigatorul web.
	- Preferințe
		- Avansat -> General -> Navigare -> Folosește derularea lină -> Fals;
		- Debifează Prompt integration at every website.
	- Opțiuni VimFX
		- șterge Gmail din lista neagră
	- Preferințe extensie: Gestionar de sesiuni
	    - General > Salvare și restaurare > Salvare sesiune > Number of back button history entries per tab to save > -1 (toate)
	- adaugă cuvântul cheie (keyword) 'b' pentru motorul de căutare Bing

- Instalez pachetul `cheese` - pentru webcam (la laptop, de exemplu)
	- https://help.ubuntu.com/community/Webcam.

- Pictograma bateriei de pe bara de sus (de meniu a sistemului): clic -> Show Time in Menu Bar (pe Laptop).

- Instalează pachetul 'chromium-browser' sau Chrome
	- Activează sincronizarea (sync);
	- Set it as the default browser;
	- Open Pocket app and let it sync, add it to the launcher;
	- În Chrome, după ce se sincronizează extensiile, în opțiunile extensiei Google Translate verific să fie activat butonul de popup și pe paginile care sunt în limba mea (română).
	- Activez Click-to-Play: [chrome://settings/content](chrome://settings/content) (setarea asta se sincronizează, din câte văd);
	- Activez următoarele flaguri în [chrome://flags](chrome://flags):
		- [chrome://flags/#enable-tab-audio-muting](chrome://flags/#enable-tab-audio-muting)
		- #disable-hyperlink-auditing
		- #enable-smooth-scrolling
		- #enable-devtools-experiments - then in devtools enable experiments such as Canvas inspection, Toolbar customization...
		- #enable-download-resumption
		- eventual #ignore-gpu-blacklist => Canvas, Flash accelerate hardware (nu am măsurat beneficiile,
		procesorul e destul de folosit și cu opțiunea aceasta activată) -> mai bine nu, apar probleme cu redesenarea paginilor la anumite schimbări, la fel și la flash. Fără această opțiune activată, nu apar așa des, sau chiar deloc. - FALS, apar, și la fel de neplăcute sunt. Nu cred că Smooth scrolling e de vină pentru că și la trecerea de la un tab la altul, fără derulare, imaginea paginii rămâne fixă.
			- It's a memory hog. YouTube and GPU process use a lot of RAM. Killing the GPU process restarts it with low RAM usage.
			From what I've seen in the Chromium Task Manager:
				- the memory hog is not because of Flash or YouTube although they take up RAM too.
				- the memory hog does not appear immediately at start up (constant 17.004K after startup of Chromium, with music in YouTube playing - a little scrolling and tab closing raised this to 60.532K, Smooth scrolling is the problem?).
	- In Chrome Developer Tools settings, enable 'Disable cache while Devtools is open' option.
	- Vimium extension options > remove Gmail from the list of excepted websites.
	- Chromium > Tab Ahead icon -> Options -> All Windows
	- If some extensions don't work, do the following to update chromium-browser to the latest version
		- BUG: chromium-browser is at old version 29 in the official repositories. Walkaround:
			- http://askubuntu.com/questions/89058/how-to-install-the-latest-stable-version-of-chromium
			- http://askubuntu.com/questions/317201/how-do-i-install-the-latest-version-of-chromium-in-ubuntu-13-10
			- http://askubuntu.com/a/368908/29733
				- `$ sudo add-apt-repository ppa:ubuntu-mozilla-security/ppa` then check for updates

- Configurări de sistem - Toate configurările
	- Aspect > Comportament > Add show desktop icon to the launcher > On.
	- Aspect > Aspect > Dimensiunea iconițelor din lansator > 33.
	- Aspect > Setez fundalul mov.
	- Aspect/Appearance > Comportament/Behavior > Show the menus for a window > In the window's title bar
	- Aspect > Setez tema la Radiance în loc de Ambiance.
	- Security & Privacy > Search > Include online search results > Off.
	- Afișaje > Margini lipicioase > Off.
	- Mouse & Touchpad > Maus > Pointer speed > 50%.
	- Consum > Suspendă dacă este inactiv pentru > 10min.
	- Ora și data > Ceas > În ceas arată: +Zi din săptămână, +Dată și lună, +Secunde.
	- Ora și data > Ceas > dezactivat (fără ceas în bara de sus)? Repornește calculatorul.
	- Brightness and Lock - limite, valori mai mici la Laptop;
	- Software & Updates (Programe și actualizări) > Actualizări > Notify me of a new Ubuntu version > For any new version.

- Terminala
    - Instalează pachetul apt „fish”, apoi instalez conform instrucțiunilor din
      [depozitul său GitHub](https://github.com/oh-my-fish/oh-my-fish) scriptul `oh-my-fish`, instalez tema
      [`bobmyfish`](https://github.com/oh-my-fish/oh-my-fish/blob/master/docs/Themes.md#bobthefish) și
      pentru ca aceasta să fie afișată corect de terminal, folosesc un font
      special de
      [aici](https://github.com/ryanoasis/nerd-fonts#option-3-install-script), acum folosesc [fontul Hack](https://github.com/source-foundry/Hack) și sunt perfect mulțumit. Pentru ca fish să fie în loc de bash în orice terminal, folosesc comanda:
       `chsh -s /usr/bin/fish` și dau un log out apoi un log in la sistem,
       conform: https://askubuntu.com/a/26440/29733, dar astfel în terminalele nou deschise nu se mai încarcă `.bashrc` deci în loc de asta, adaug la sfârșitul `.bashrc` linia `exec fish`.
    - Editare -> Preferințe profil
        - Dacă nu folosesc fontul Hack sau altul pentru fish: Generale -> Font -> Monospace 10;
        - Derulare -> Derulează înapoi -> Nelimitat.

- Remove from launcher: Amazon, Ubuntu One, Ubuntu One Music, LibreOffice apps.
- Add to launcher: GNOME Terminal, PasswordSafe, Chromium, Sublime Text.

- Install PasswordSafe: http://sourceforge.net/projects/passwordsafe/files/Linux-BETA/
	- BUG: no PPA, no automatic updates (like on Windows, actually)
		- http://sourceforge.net/p/passwordsafe/discussion/134801/thread/f3c0bdc1/
		- http://sourceforge.net/p/passwordsafe/support-requests/380/
		- http://sourceforge.net/p/passwordsafe/discussion/search/?q=PPA
		- Walkaround: ??
			- https://launchpad.net/+search?field.text=passwordsafe
			- https://bugs.launchpad.net/pasaffe/+bug/1190506 „Pasaffe is Password Safe compatible”
				- BUG: can't hide password with stars in edit dialog
				- BUG: less features
				- I'm not sure how can a Python app be secure enough to handle password management

	- Options > System:
		- Allow multiple instances > False;
		- Put icon in system tray > False.

- Probleme cu funcția de Sleep și Lock
	- „artefacte vizuale” după revenire și sistem nefuncțional
		- Încearcă un driver proprietar în loc de nouveau (open source). Dacă 'Toate configurațiile -> Software & Updates -> Additional Drivers' nu merge încearcă cu 'sudo apt-get install NAME' unde NAME e de exemplu 'nvidia-319-updates'.
		Apoi, pentru Sleep poate va fi necesar să folosești butonul fizic de pornire a PC-ului ca să trezești calculatorul. Dacă Internetul nu merge după trezire din Sleep, rulează "sudo dhclient eth0" (vezi http://askubuntu.com/a/12179/29733) sau și mai bine, `sudo service network-manager restart` care actualizează și indicatorul de conexiune la Internet al Unity arătând că conexiunea este stabilită (http://askubuntu.com/a/251946/29733). Pentru a realiza asta în mod automat (comportamentul așteptat) vezi următoarele pagini:
			- https://bugs.launchpad.net/ubuntu/+source/network-manager/+bug/1130571 (My Bug, I think)
				- linked walkaround: http://www.webupd8.org/2013/01/fix-wireless-or-wired-network-not.html
				- not working
				- http://ubuntuforums.org/showthread.php?t=1401142
				- http://askubuntu.com/questions/89744/suspending-computer-and-maintaining-internet-connection?rq=1
				- http://askubuntu.com/questions/190340/is-there-a-way-to-suspend-without-turning-off-network
				- http://askubuntu.com/questions/216110/how-do-i-find-what-kernel-module-is-behind-a-network-interface
				- http://askubuntu.com/questions/279584/suspend-resume-failure
				- http://askubuntu.com/questions/104710/how-to-restore-ethernet-connection
				- http://forum.mandriva.com/en/viewtopic.php?t=118414
				- https://help.ubuntu.com/community/NvNetInstallation
			- https://bugs.launchpad.net/ubuntu/+source/network-manager/+bug/274405
			- Also see the 'lsmod' command where you can see forcedeth listed.
			- Associated command: `sudo gedit /etc/pm/config.d/unload_modules`
    	- **Walkaround** - In `/etc/pm/sleep.d`, add a text file ~`broken_network_after_resume_walkaround` and run: `sudo chmod +x broken_network_after_resume_walkaround` then it has those permissions: (-rwxr-xr-x). Contents of this file:
            ```
			#!/bin/bash
            # inspired from http://askubuntu.com/a/209855/29733
            case "$1" in
                hibernate|suspend)
                    # do stuff on suspend
                    ;;
                thaw|resume)
			        # do stuff on resume
                    sudo service network-manager restart
                    ;;
            esac
			```
        	To take effect there is no need to do anything else: no restart, no other command to run.

- `mkdir ~/bin` then add `~/bin` to `$PATH` using *fish*:
  - create or modify the file `~/.config/fish/config.fish`:
    - append
		```
		set PATH "$PATH:/home/silviu/bin:/home/silviu/opt/todo.txt-cli/bin"
		alias t todo.sh
		```

- Install Node.js
	- For a recent version of nodejs and a recent version of npm (>1.3) which is needed for 'grunt' 4.1 from the npm registry which is to be installed once in each of the project folders using Grunt.js, run these lines: taken from https://github.com/IonicaBizau/dotfiles/blob/master/apps/node.sh (another source: https://github.com/gruntjs/grunt/pull/886#issuecomment-27914161):
		```
		sudo add-apt-repository -y ppa:chris-lea/node.js
		sudo apt-get update
		sudo apt-get install nodejs
		```
		- Update: this PPA is not updated anymore, no versions for Ubuntu Vivid Vervet 15.04, bower npm package requires a newer version of nodejs than available in this PPA.
        - Alternatives:
            - https://github.com/nodesource/distributions (tested) (found on this page: https://github.com/nodejs/node-v0.x-archive/wiki/Installing-Node.js-via-package-manager)
            - Install nodejs with nvm (advice from Ionică Bizău) so I have the latest Node.js version: v4.0.0.
	- Because the executable name is the unusual and pretty unsupported (by grunt, for example) 'nodejs':
		```
		ln -s /usr/bin/nodejs ~/bin/node
		```
        - https://github.com/IonicaBizau/dotfiles#npm-config for configuring npm to globally install without sudo
	- Install npm packages: share-term, jsdoc.

- Install git, restore .ssh data.
- Install npm
	- Then install the `grunt` npm package: `sudo npm install -g grunt-cli`.

- Install 'gufw' (firewall GUI) then enable the firewall by using it.
	- note: after reboot the firewall is still enabled.

- BUG: before logging in, the order of the displays is inverted, I've repaired that in Unity using the settings in Afișaje, after starting to use proprietary NVIDIA driver.

- Install Visual Studio Code from https://code.visualstudio.com/ (they have .deb packages).

- Enable night light mode („Lumină nocturnă”) in System Settings.

- As an alternative for the not-working-in-wine Evernote 5, try https://github.com/nvbn/everpad (not working now).
	- BUG: after uninstalling Evernote 5.0.3 in Wine, the icon does not disappear from Unity Dash.
		- Links:
			- http://askubuntu.com/questions/339763/cant-remove-the-icon-of-a-wine-application-from-unity-dash-home
				- Walkaround: delete the Evernote.desktop file, and also remove it from Trash (Unity Dash seems to search the Trash for .desktop files too! - bug to report).
	- BUG: everpad crashes and it's indicator menu is not working:
		- https://github.com/nvbn/everpad/issues/371;
		- https://github.com/nvbn/everpad/issues/369.

- În Gedit:
  - Install the package with the name aproximatively `gedit-plugins` and configure the newly installed plugins, maybe get inspiration from them to have new functionalities in VS Code via plugins.

- Instalează și configurează Dropbox
	- Dropbox indicator -> Preferences... -> Bandwidth -> Upload rate -> Don't limit.

- I could try this answer to bring back the app indicators: http://askubuntu.com/questions/362135/how-to-re-enable-tray-icons-for-applications-in-ubuntu-13-10 (Dropbox is already visible, I would need that only for redshift/f.lux currently, but later probably for pidgin and others...).
	- Search link: http://askubuntu.com/search?q=13.10+indicators.

- Install ubuntu-tweak after adding this PPA: https://launchpad.net/~tualatrix/+archive/ppa (only if I start using some option in it).
  - 1. Open GNOME Tweaks
    2. Select ‘Top Bar’
    3. Slide “Battery Percentage” setting to ‘on’

- Install VIM
    - Copy [the `.vimrc` file from my `dotfiles` GitHub repo](https://github.com/silviubogan/dotfiles/blob/master/.vimrc), install Vimium (see the readme
      file in their GitHub repository) (- here I think I wanted to write Vundle
      instead of Vimium) and then install all the plugins in the
      `.vimrc` file with `:PluginInstall`.
	Configurare VIM:
	- Pentru ca "*y și "*p să funcționeze (copiere și lipire în clipboard-ul sistemului), instalez pachetul vim-gtk și verific cu comanda `:echo has('clipboard')` să se afișeze 1, nu 0. De asemenea, acest pachet schimbă și titlurile terminalelor cu VIM în „[nume fișier] [un + dacă fișierule modificat] ([cale către fișier]) - VIM”.
	- E bine să fac copie de siguranță înainte de instalarea sistemului la `.vimrc`, sau să pun ultimele modificări [în depozitul meu `dotfiles`](https://github.com/silviubogan/dotfiles/blob/master/.vimrc).

- Install git
	- Removing --global from the following git-config commands only sets the option for the repository in the current directory.

		```
		git config --global color.ui
		```
		In git 1.8.4 this is the default, but it's not in Ubuntu's official software sources yet.
		- But it can be installed, and it's stable: add `ppa:git-core/ppa` (https://launchpad.net/~git-core/+archive/ppa) to your system's Software Sources then check for updates and install the available updates.
	```
	git config --global core.editor "vim"
	```
	- or see http://stackoverflow.com/questions/2596805/how-do-i-make-git-use-the-editor-of-my-choice-for-commits
	```
	git config --global user.email "..."
	git config --global user.name "..."
	git config --global push.default simple
	```
	- about the last line: otherwise, 'git push' will print useless things about a future change in the default behavior of running 'git push'. The current behavior is 'matching' which means pushing all the branches to the remote. In git 2.0, the behavior will be 'simple' which means pushing the active branch to the correspondant upstream branch if they have the same name.
	- When making the first push after setting up the ssh, checking the checkbox in the password dialog will make it never appear again and the pushes will just work.
	- Toate setările globale Git pe care le folosesc:
		```
		$ git config --global -l
		user.email=silviubogan@gmail.com
		user.name=Silviu Bogan
		alias.co=checkout
		alias.br=branch
		alias.ci=commit
		alias.st=status
		alias.cl=log --graph --color --decorate --all --date=relative
		core.autocrlf=input
		core.editor=code --wait
		core.filemode=false
		credential.helper=cache --timeout=3600
		```
	`alias.cl` este deosebit de folositor: în directorul unui depozit rulez `git cl` și istoria depozitului este afișată complet, cu mai multe detalii și colorat.
	`credential.helper` este recomandat de GitHub (HTTPS e recomandat în loc de SSH).

- Install nixnote, because everpad doesn't work currently (3 nov 2013): http://ubuntuhandbook.org/index.php/2013/07/install-nixnote-ubuntu-13-10-linux-mint/
	- everpad works (5 nov 2013), install it (https://github.com/nvbn/everpad), enable 'Start with system' setting, but it has big bugs:
		- it has problems with sync, sometimes it doesn't finish syncing
		- it also breaks my special characters and diacritics
	- I think I'll use NixNote, I'm watching everpad on GitHub.

- I had a situation in which no sound would work, and not only this, but the apps which should be playing sounds (YouTube players, local music app) were broken, the playback cursor remained at the beginning of the song.
I've done `sudo alsa force-reload` and then I was able to launch `alsamixer` in terminal, but still no sound. And then I rebooted. The sound worked again. Links:
	- http://askubuntu.com/search?q=no+sound+after+resume
	- http://askubuntu.com/questions/190146/no-sound-after-suspend-resume

- BUG: one or two times, the user menu (with that 'settings'-like icon - toothed wheel) disappeared from the top bar: http://askubuntu.com/questions/201263/shutdown-and-user-button-missing-in-panel.

- BUG: https://bugs.launchpad.net/ubuntu/+source/gnome-settings-daemon/+bug/1232454 : After resume from suspend, a window appears saying that the system will suspend very soon because of inactivity. If enough time has elapsed between the suspend and the resume, more windows will appear saying the same thing. The options in the window are OK - suspend now, and Cancel.
	- There is a walkaround described in the bug report comments. I did not test it.

- Install `rar` and `unrar` packages
	- .rar archives are not supported by default. you must install rar and unrar packages (a prompt does this for you when you first open a .rar file)

- Install https://github.com/k4rthik/git-cal (it's really nice)
	- when installing, KEEP THE installed commit so you can uninstall it if you want

- Install mind-mapping software:
	- Install FreeMind (also Anki, maybe) for learning:
		- FreeMind - if the latest version is not in the Software Center, from this page: http://freemind.sourceforge.net/wiki/index.php/Download download this: OS: „Any | binaries for any operating system - max | All-inclusive” version
			- put the contents of the archive in ~/freemind, then run the program using `freemind.sh` or lib/freemind.jar in that folder (but run `chmod u+x freemind.sh` before)
		- bug: with FreeMind 1.0.0 on Ubuntu 13.10 x64 I couldn't open a file created with FreeMind 0.9. I stayed with the old version available in the Software Center
		- bug: text does not look clear after first zoom
	- Or instead of FreeMind install XMind (http://www.xmind.net/)
		- Features:
			- open-source, prettier, supports import/export from/to FreeMind format
			- FreeMind exports HTML, interactive HTML, flash, PNG, JPEG, TWiki, Java applet
			- XMind (the free version) exports HTML, text, image, FreeMind
			- automatically checks for updates
		- BUG: In XMind sometimes I can't open the menus in the menu bar using the mouse (it's a problem related to the Unity global menu) but I can press Alt+F then use the arrow keys to navigate in and between the menus. Maybe the next version of ubuntu (14.04) will allow me to deactivate the global menu just in XMind.
		- BUG: only at zoom 100% the text is not cut
		- BUG: does not support rich text nodes and moving the mind map view uses the middle mouse button which is harder to press
		- After install:
			- Preferences -> General -> Startup -> When XMind starts: -> Open maps unclosed last time.
	- http://alternativeto.net/software/freemind/

- If the clock in the top panel happens to disappear, run this command:
    `killall unity-panel-service`
    - source: http://ubuntuforums.org/showthread.php?t=2181988
    - google search: "ubuntu 13.10 the clock disappeared"

- Rulez comanda `sudo apt-get install dos2unix` în Terminal, pentru a putea folosi mai târziu comenzile unix2dos și dos2unix pentru convertirea caracterelor de sfârșit de rând (de exemplu, când pun un fișier text în Dropbox/Partajate).

- Pentru comanda 'tree', rulez: `sudo apt-get install tree`.

- Pentru aflarea temperaturii CPU: http://askubuntu.com/questions/15832/how-do-i-get-the-cpu-temperature
	```
	$ sudo apt-get install lm-sensors
	$ sudo sensors-detect # Răspund cu da la toate sau aproape toate întrebările
	$ sudo service kmod start
	$ sensors
	```

- Instalez TeamViewer x86: http://www.teamviewer.com
	- versiunea x64 pentru Debian/Ubuntu are o „dependență nesatisfăcută”.

- Instalez audacity pt. înregistrare sunet. https://help.ubuntu.com/community/AudioCapture

- TODO: automontarea partitiei Files, pentru inregistrearea automata a melodiilor in programul de ascultare de muzica Rhythmbox, dar sa vezi doar melodiile din partitia Linux, si asta poate prezenta avantaje sau fi de dorit.

- Alt program folositor de instalat (URI-uri de introdus în Chrome): [apt://unity-tweak-tool](apt://unity-tweak-tool) (o instalez și când o deschid apare mesajul:
	- > The following schema is missing
	  >
	  > com.canonical.unity.webapps
	  >
	  > In order to work properly, Unity Tweak Tool recommends you install the necessary packages.

	- Pe askubuntu problema se rezolvă astfel:
		```
		sudo apt-get install unity-webapps-service
		```
	- Configurare
		- Unity > Launcher > Behaviour > Minimize single window applications on click > True
		- Window Manager > Hotcorners > Behaviour > Top-left: Show Workspaces

- Sigur folositoare, necesare chiar:
https://apps.ubuntu.com/cat/applications/ubuntu-restricted-extras/ (pentru redare MP3-uri etc.)
- Instalez VLC, GIMP.
- Instalez Skype
	- instalez de pe site-ul oficial www.skype.com sau din Ubuntu Software Center DAR în 29.07.2017 în Ubuntu Software este o versiune nefuncțională de Skype și pe site-ul www.skype.com e o versiune funcțională;
	- restartez Unity dacă nu găsesc în Dash pictograma Skype să o trag pe bara din partea stângă cu programe, și dacă nu se lipește de bară, deschid Skype și apoi fac clic dreapta pe pictograma apărută pe bară și selectez `Blochează pe lansator`.

- Instalez drivere grafice și de altă categorie din
Configurări de sistem > Programe și actualizări > Drivere adiționale (Pe laptop am avut inclusiv o actualizare a Processor microcode firmware for Intel CPUs).

- Instalez `trash-cli` cu comanda `sudo apt-get install trash-cli` pentru comanda
`trash` ca să nu șterg definitiv fișiere din greșeală cu `rm`.

- Configurez LibreOffice Writer
	- Unelte > Opțiuni > LibreOffice > Vizualizare > Șoricel > Buton mijloc mouse > Derulare automată.

- Instalez pachetul `colordiff` conținând comanda `colordiff`:
	- pentru diff colorat.
	- Vezi http://stackoverflow.com/a/8800636/258462.

- Instalez `corebird` (client Twitter drăguț, pentru care pachete se găsesc greu):
	- PPA: https://launchpad.net/~twolife/+archive/ubuntu/desktop
		- Sursa: http://www.omgubuntu.co.uk/2014/11/linux-twitter-app-corebird-new-release/?utm_source=website&utm_medium=carousel&utm_campaign=carousel

- Vezi aplicațiile din articolul: http://www.omgubuntu.co.uk/2014/11/useful-tools-for-ubuntu-do-you-use-them/?utm_source=website&utm_medium=carousel&utm_campaign=carousel (după ce încerc Linux Laptop Tools sau cum se numește, poate șterg link-ul din acest fișier).

- În `~/.bashrc`, în caz că prompt-ul terminalului nu este colorat, modific să fie cu `yes` astfel:
	```
	force_color_prompt=yes
	```

- Install Docker,
	apoi trebuie în /etc/apache2/apache2.conf să adăugăm la final rândul „ServerName localhost”. Dacă rulăm `sudo apachectl start` în
terminal, putem deschide http://localhost/ în browser. Rădăcina implicită a documentelor
Apache pe Ubuntu este `/var/www/html`. Scripturile PHP astfel funcționează. Pentru
a reporni doar serverul mysql, folosim `sudo systemctl restart mysql`. Modificări esențiale făcute la fișierul `/etc/apache2/apache2.conf` și în directoarele `/etc/apache2/sites-enabled`, `/etc/apache2/sites-available`:
	- `apache2.conf` conține printre altele:
		```
		<Directory /home/silviu/www/>
			Options All
			AllowOverride All
			Require all granted
		</Directory>
		```
	- în fișierele `000-default.conf` din celelalte două directoare pun liniile:
	    ```
		DocumentRoot /home/silviu/www
        DirectoryIndex index.php index.html
		```

- GitHub recomandă folosirea Git prin HTTPS, nu prin SSH. Pentru asta vezi [acest articol oficial](https://help.github.com/articles/caching-your-github-password-in-git/). Pe scurt, execut două comenzi prin sudo:
	```
	$ git config --global credential.helper cache # Set git to use the credential memory cache
	$ git config --global credential.helper 'cache --timeout=3600' # Set the cache to timeout after 1 hour (setting is in seconds)
	```

- Setez în Configurări de sistem > Hardware > Tastatură > Scurtături, scurtătura `Ctrl+Shift+Esc` comenzii `gnome-system-monitor` (pentru când SO nu mai funcționează și trebuie să forțez terminarea unui proces).

- Ca alternativă la Paint.NET pentru Ubuntu, folosesc Pinta:
	- https://pinta-project.com/pintaproject/pinta/.


- Enable Minimise on Click in GNOME Shell
  - `gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'`

- Change Touchpad Scroll Direction
  - 1. Open Settings
    2. Go to Mouse & Touchpad
    3. Slide the “Natural Scrolling” toggle to on

- Install Telegram, Tilix, Flameshot, Neofetch, cryfs, todo.txt-cli
- `sudo snap install cawbird`

- `/.bashrc` contents until I fully switch to fish:
	```bash
	export NVM_DIR="$HOME/.nvm"
	[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
	[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion


	function cd_up() {
		cd $(printf "%0.s../" $(seq 1 $1 ));
	}
	alias 'cd..'='cd_up'

	export EDITOR="code"
	```

- Install backups of shell scripts into `~/bin`.

- Instalez actualizări.
- La final rulez și:
	```
	$ sudo apt-get autoremove
	```

## La reinstalarea Ubuntu
Fac copie de siguranță la depozitele apt din Surse Software, inclusiv cele dezactivate care s-ar putea să înceapă să funcționeze din nou.

Make backups of shell scripts from `~/bin`.