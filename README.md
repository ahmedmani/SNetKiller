very simple and quick:
the app uses frida to inject an agent into google services and prevent it to access certain files.
for me, running latest magisk, was enough to return "file not found" at the various su paths and common
binaries paths but later, it is checking for more things such as current selinux status, all the packages etc.
more rules will be added eventually... I don't really like the fact i can't play certain games or
use certain applications because i have my phone rooted.

this makes snet believe we are good guys and bypass safetynet attest on apps which just check for basic integrity (which is what i was needing).
you can use logcat and grep SNKiller to see what files are currently accessed.
feel free to pr your patches to the agent if needed.

## before
![Alt text](/screen_before.png?raw=true "Optional Title")

## after
![Alt text](/screen_after.png?raw=true "Optional Title")

Changelogs:
2019-06-23
* added support for x86

2019-06-22
* everything was seriously returning -1 for a typo in faccessat
* let it believe we are in Enforcing selinux context, always
https://github.com/iGio90/SNetKiller/blob/master/app/src/main/assets/agent-2019-06-22.js

* init
2019-06-21

you can install app-debug.apk and use the unique button available