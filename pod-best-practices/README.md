# Pod Best Practices

This simple change can make your applications 10x secure.

By default, Pods are designed to access everything and do anything. So make sure to configure your pods with the right settings:

• 𝗿𝗲𝗮𝗱𝗢𝗻𝗹𝘆𝗙𝗶𝗹𝗲𝗦𝘆𝘀𝘁𝗲𝗺: Will mount the container’s root filesystem as read-only.

• 𝗮𝗹𝗹𝗼𝘄𝗣𝗿𝗶𝘃𝗶𝗹𝗲𝗴𝗲𝗘𝘀𝗰𝗮𝗹𝗮𝘁𝗶𝗼𝗻: Will make sure the process doesn't get more privileges than the parent process.

• Using 𝗿𝘂𝗻𝗔𝘀𝗡𝗼𝗻𝗥𝗼𝗼𝘁 and 𝗿𝘂𝗻𝗔𝘀𝗨𝘀𝗲𝗿 collectively may not work as expected in some of the scenarios. So use it cautiously.

• 𝗖𝗮𝗽𝗮𝗯𝗶𝗹𝗶𝘁𝗶𝗲𝘀: Works at the Linux Kernel level, to set micro privileges for the processes.