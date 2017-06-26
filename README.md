# About
This is a python IMAP client for filtering email messages.
Although it's more a hack than a finished project and 
tailored to my personal needs, it still might
be useful to others. It is not a plug&play solution but
requires at least basic Python programming skills to 
configure filter rules. In contrast to other solutions,
this script minimizes requirements on the IMAP server by
filtering locally and by relying on polling instead of
server side notifications.

I use this client to sort my work email which resides 
on an ancient version of Groupwise which caused problems
with the IMAP filters I tried before.

# Install
1. Of course, you need a python installation ;-). Add 
   the python imapclient module, e.g. using `pip`: 
   ```bash
   pip install imapclient
   ```
1. Enter the credentials for your IMAP server 
   into `imapfilter.conf` and protect them:
   ```bash
   cp imapfilter.conf-simple imapfilter.conf
   chmod 600 imapfilter.conf
   vi imapfilter.conf
   ```
1. Edit the filter rules in the `apply_rules` function
   of `imapfilter.py`. You might also want to have a
   look at the constants at the beginning of the file.
1. After testing, you might want to autostart 
   `imapfilter.py` using systemd on a linux box.
