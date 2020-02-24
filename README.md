My personal build of st (based on 0.8.2)
========================================
ST is a simple terminal implementation for X.

Requirements
------------
In order to build st you need the Xlib header files.

Installation
------------
Edit config.def.h to configure

Afterwards enter the following command to build and install st (if
necessary as root):

`sudo make clean install`

Patches
--------
_All patches are added via branches. Source: [here](https://st.suckless.org/patches/)_
- anysize
- desktopentry
- clipboard
- scrollback
- vertcenter

**Patching guide**
refer to [here](https://github.com/qguv/dwm) for an example
- Add a patch:
    - branch off of develop
    - apply patch
    - move all config.def.h changes to config branch
    - commit branch `git commit -m <branchname>`
- Delete a patch:
    - Delete branch locally
        `git branch -D <branchname>`
    - Delete branch remotely
        `git push origin --delete <branchname>`
- Merge to develop (in order to build):
    - Reset develop branch
        `rm -rf config.h && sudo make clean`
    - Merge all branches
        `git merge <branchname> m <branchname>`
