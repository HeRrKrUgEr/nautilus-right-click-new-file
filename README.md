# Right-click New File Context Menu for Nautilus / Gnome File Manager
Super easy and light script to automate adding a context menu to Nautilus / Gnome Files to create a new document.

Built in GNOME nautilus 3.22.3; not tested in other versions.

Before:

![nautilus right click context menu - before](./img/nautilus-right-click-before.png)

After:

![nautilus new file context menu - after](./img/nautilus-right-click-new-file.png)

## Download the script
Run via terminal:
```bash
git clone https://github.com/angela-d/nautilus-right-click-new-file.git && cd nautilus-right-click-new-file
```
Confirm you're in the right directory:
```bashrc
ls
```
You should see:
```html
img  LICENSE  nautilus-newfile-contextmenu.sh  README.md  Templates.tar.gz
```

Now, run the script:
```bashrc
./nautilus-newfile-contextmenu.sh
```

That's all there is to it!

***

# (optional) Manual Instructions (if you don't want to run the automated script)
* Download Templates.tar.gz and extract
```bash
tar -xvzf Templates.tar.gz
```
* Move the extracted files (templates) into /home/Templates/

(in Nautilus; Open File Manager -> Click Home on the left -> If *Templates* folder does not exist, create it)

* If your changes to do not automatically appear, log out or run:
```bash
xdg-user-dirs-update
```
to generate the user-dirs config file.

Done!

## Note
Each of the template files have a prefix like `#!/usr/bin/env php` when you open the file (except the Text file & Writer/Word .doc) - for any of the files, short of the empty bash file, this prefix is not required and can be deleted when you've created a new file on your desktop or file manager.

These were added so Linux could interpret the type of file and automatically create the context menu icon without any extra code.

***

#### (optional) Customize your Context Menu ####
In Nautilus, navigate to the Home directory and then Templates.

Here, you can place your dummy files (templates) in folders for easy sorting, or add new ones.

If your changes are not instantaneous, restart Nautilus:
```bash
nautilus -q && nautilus &
```
In some instances, you may have to log out and log back in.

#### (optional) Prevent Nautilus from breaking desktop icons ####
In 3.26, Nautilus will be breaking desktop icons.

To prevent this from occurring, prevent Nautilus from updating (if you've already updated, you'll have to downgrade the pacakge in order for the hold to be effective).

In Debian / Ubuntu (and deriatives):
```bash
apt-mark hold nautilus
```
Note: This will prevent the Nautilus package from updating, you will not receive future bugfixes until you undo the hold.

Ubuntu users: [Ubuntu 18.04 LTS will be sticking with an older version of Nautilus](https://www.omgubuntu.co.uk/2018/01/ubuntu-18-04-lts-will-ship-older-version-nautilus) due to the desktop icons being taken out.
