## Collection of user experience defects related to Plasma and KDE software
This is a personal notebook to collect issues encountered in my daily experience with the Plasma desktop and [KDE Software](https://www.kde.org).

### Login and logout
* **A login after a logout sometimes results in Plasma hanging** for a long time before loading the desktop (if even). Not many users encounter this as logout/login cycles are rare in the typical use case of a personal PC. This has been reported in [Fedora](https://bugzilla.redhat.com/show_bug.cgi?id=1742893). The root may be user processes hanging after the logout. Possibly this was related to [**KDE bug 424408** (Multiple coredumps with every login/logout)](https://bugs.kde.org/show_bug.cgi?id=424408) that is marked as solved. To be verified.

### Look and feel ###
* **Some UI elements have bad rendering with fractional scaling**. This issue may present itself across several Plasma components, and it may not be obvious that the root cause is more general and related to a component called [QQC2-Desktop-Style](https://api.kde.org/frameworks/qqc2-desktop-style/html/index.html). The issue is tracked in [**KDE bug 414266** (Certain (not all) QQC2 buttons have vertically stretched and pixellated text when fractional display scaling is used)](https://bugs.kde.org/show_bug.cgi?id=414266) for which a solution has been proposed but it requires a quite industrious implementation. It seems the plan is a transition to a differently-based sytle: [QQC2 Breeze Style](https://invent.kde.org/plasma/qqc2-breeze-style). More in general, fractional scaling is unfortunately very complicate to get right, but KDE is doing a fairly good job with it.

### Removable storage
* **KDE is unable to properly report the progress of file transfers**, and this is especially evident for slower USB storage devices. This issue is tracked in [**KDE bug 281270** (When copying files to a removable disk, speed and progress reflect copying to the local cache not to the disk itself)](https://bugs.kde.org/show_bug.cgi?id=281270), open since 2011 and so far with no solution in sight.

### Wayland
* **Selection and paste issues**, in particular the selection and middle-click paste across different application may not work for non Wayland-native software running on XWayland. This has been fixed between GTK and Qt, but not for applications using other graphics libraries. The general issue is tracked in [**KDE bug 422426** (Implement Wayland Primary Selection Protocol bridge with XWayland)](https://bugs.kde.org/show_bug.cgi?id=422426).
