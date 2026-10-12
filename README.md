# local.icontasks

Fork of KDE Plasma 6.7.5's Icons-Only Task Manager (`plasma-desktop/applets/taskmanager`) with a configurable icon size.

- New setting `iconSize` (px, 0 = automatic) in Configure -> Appearance -> "Icon size".
- Icon is clamped to the task cell, so larger sizes need a thicker panel.
- Installed as a separate applet id `local.icontasks`; the stock applet is untouched.

## Build / install

    cmake -S . -B build -G Ninja -DCMAKE_INSTALL_PREFIX=$HOME/.local
    cmake --build build
    sudo install -Dm755 build/bin/plasma/applets/local.icontasks.so /usr/lib64/qt6/plugins/plasma/applets/local.icontasks.so

Then replace `plugin=org.kde.plasma.icontasks` with `plugin=local.icontasks` in `~/.config/plasma-org.kde.plasma.desktop-appletsrc` and restart plasmashell.

Needs the Plasma/KF6 `-devel` packages (libplasma, plasma-workspace, plasma-activities(-stats), kf6-kio, kf6-knotifications, libksysguard, kf6-kitemmodels).

License: GPL-2.0-or-later, derived from KDE plasma-desktop.
