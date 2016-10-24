# Setup

### Ubuntu

https://www.dartlang.org/install/archive

Download *Dart SDK* and *Dartium* of version 1.20.1 to /home/droid/software/Dart/dart-1.20.1

*Dart SDK*: /home/droid/software/Dart/dart-1.20.1/dart-sdk

*Dartium*: /home/droid/software/Dart/dart-1.20.1/dartium-linux-x64-stable-1.20.1.0

**Creating a project in IntelliJ**

![](_misc/Creating%20a%20new%20Dart%20project.png)

Add path to Dart SDK. As soon as the path to Dart SDK is added, a list of templates are displayed.

![](_misc/On%20adding%20Dark%20SDK%20path.png)

Add path to Dartium as well.

![](_misc/Adding%20Dartium%20path.png)

Choose any template that is needed and proceed to create an application.

**Replacing an earlier installation of Dart**

*Earlier Installation*

```sh
~$ which dart
/usr/bin/dart
~$ dart --version
Dart VM version: 1.13.2 (Tue Jan  5 16:03:09 2016) on "linux_x64"
```

*Determining the path to previous installation*

```sh
droid@droidserver:~$ ls -la /usr/bin/dart
lrwxrwxrwx 1 root root 20 Jan  5  2016 /usr/bin/dart -> ../lib/dart/bin/dart
droid@droidserver:~$ ls -la /usr/lib/dart/bin/dart
-rwxr-xr-x 1 root root 9859832 Jan  5  2016 /usr/lib/dart/bin/dart
```

*Pointing to latest Dart binary*

```sh
droid@droidserver:~$ sudo update-alternatives --install "/usr/bin/dart" "dart" "/home/droid/software/Dart/dart-1.20.1/dart-sdk/bin/dart" 1
[sudo] password for droid: 
update-alternatives: using /home/droid/software/Dart/dart-1.20.1/dart-sdk/bin/dart to provide /usr/bin/dart (dart) in auto mode
```

*Removing previous path* ?????

```sh
droid@droidserver:~$ sudo update-alternatives --remove "dart" "/usr/lib/dart/bin/dart"
```

*Verification*

Verify if *dart* now points to the latest dart installation binary.

```sh
droid@droidserver:~$ which dart
/usr/bin/dart
droid@droidserver:~$ ls -la /usr/bin/dart
lrwxrwxrwx 1 root root 22 Oct 23 23:27 /usr/bin/dart -> /etc/alternatives/dart
droid@droidserver:~$ ls -la /etc/alternatives/dart
lrwxrwxrwx 1 root root 55 Oct 23 23:27 /etc/alternatives/dart -> /home/droid/software/Dart/dart-1.20.1/dart-sdk/bin/dart
droid@droidserver:~$ which dart
/usr/bin/dart
droid@droidserver:~$ dart --version
Dart VM version: 1.20.1 (Wed Oct 12 15:07:10 2016) on "linux_x64"
```

