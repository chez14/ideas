## Adjustable Bot
I'm referencing to the how bot got triggered to do someting, explicitly on fetching things in background.

I'm imagining how CloudFlare managed to verify such a realy great number of domains and something appears on my mind how to do it, and simple.

You'll make a new table that has a "what to do", "what module/component that responsible to do it", "it's parameter", "some event rule (will be explained below)", "timestamp to do it", "timestamp of expiration", "timestamp it's done", "is canceled/deleted".
Yes you got my idea, fetch it every minutes/5 minutes/other, just make sure it's checked every periods.

The event rule are described like... "what should do when it's going to be done", "what should do when it's done", and "what should do if it's error".

Easy, quick, simple, oh i think it's not so simple. Good luck!