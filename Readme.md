#libpd [udpsend~] / [udpreceive~] fix

I posted this fix on createdigitalnoise.com forum two years ago, but since then the forum seems to be gone. Luckily I had github gists left so I could reconstruct this fix.

##Problem

Back then if you use updsend on PC to send data to updreceive on mobile, you will get a lot of jittering and interruptions, there's something odd with
scheduling, so after going through mailing lists for months, I found this solution (i.e. replace methods that came in libpd sources with the ones I've found).

Honestly, I don't remember which methods needed to be replaced (my guess is sched_tick.c), so I just saved the files code in which I replaced.

Two years ago when I posted that, I remember hearing that this problem got fixed long ago, but two years after I encountered the same issue with libpd 0.8.3, so I figured I just post it here for future releases.

##How to use
Just go to libpd directory in Pods (or whichever way you installed it), replace the files with the ones I have here, clean your build and recompile.

Note: I am doing this for iOS as you might've noticed, so I'm not sure if this problem exists on, say, Android in the first place.
