# fullscreenapplauncher
### Automator app to launch macOS apps in fullscreen

- - -

#### Manual

This app has been written to be added as a login item to launch apps at login automatically.
The following commands install the app. [It is already set to launch Terminal.app in fullscreen mode.]

&nbsp;&nbsp;**1.** Launch a terminal emulator, e.g. Terminal.

&nbsp;&nbsp;**2.** Download fullscreenapplauncher, and move it to Applications/. Enter:
```shell
cd && mkdir Tmprary && cd Tmprary && git clone https://github.com/kvpb/fullscreenapplauncher.git && cd fullscreenapplauncher && mv fullscreenapplauncher.app /Applications/
```

&nbsp;&nbsp;**3.** [Optional] Add fullscreenapplauncher as a login item. Enter:
```shell
sudo sqlite3 /Library/Application\ Support/com.apple.TCC/TCC.db "INSERT INTO access VALUES('kTCCServiceAccessibility','com.apple.automator.fullscreenapplauncher',0,1,1,NULL);" # sudo sqlite3 /Library/Application\ Support/com.apple.TCC/TCC.db "INSERT INTO access VALUES('kTCCServiceAccessibility','${px}.${dn}.${sx}',0,1,1,NULL);"
```

&nbsp;&nbsp;**3.5.** [Optional] If the bundle ID, e.g. `nd.relles.noitacilppa`, of the app is incorrect, enter:
```shell
/usr/libexec/PlistBuddy -c 'Print CFBundleIdentifier' /Applications/fullscreenapplauncher.app/Contents/Info.plist # /usr/libexec/PlistBuddy -c 'Print CFBundleIdentifier' /${Path}/fullscreenapplauncher.app/Contents/Info.plist
```
… Then copypaste the output, and go back to step 3, replacing the wrong bundle ID with the correct one from the output.

&nbsp;&nbsp;**4.** [Optional] If you want to use fullscreenapplauncher with another app, enter:
```shell
open -a Automator.app /Applications/fullscreenapplauncher.app
```
… Then replace `Terminal` with the name of the app you want and then save.

&nbsp;&nbsp;**Note:** Generic versions of those commands can be found as comments at the end of lines.

- - -

#### Version 1.00

#### Author

<p align='center'><a href='http://karlbertin.com/'><img src='https://gist.githack.com/kvpb/bfed748ac5c509985c89ea613a2bfd02/raw/8c0b311b7c848fabddf61672ba6bb72c8754fed9/karlbertinssymbol.svg'></a><br><b>Karl V. P. Bertin `<code>kvpb</code>`</b><br>
<a href='https://www.linkedin.com/in/karlbertin'>LinkedIn</a> | <s><a href=''>Facebook</a></s></p>
