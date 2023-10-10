Install the netcat nc command with Homebrew (otherwise Mac OS X version is really old and the interface is different):

brew install netcat
Use netcat to listen for incoming TCP connections on port 3000:

nc -l -p 3000
Note: old versions of netcat consider using -l and -p incorrect usage
e.g. this would work instead for old versions of netcat nc -l 3000

This instance of netcat is considered a "listener" and is now waiting for a connection.

Once you connect to the listener, the connection will act like a channel/pipe.

Use netcat to establish a TCP connection (run in a new terminal window so as to not conflict with listening netcat instance):

nc localhost 3000
You've set up both ends of the TCP connection. If you type into one of those terminal windows and hit <Enter>, you should see whatever you typed appear in the other window. Any data put through one end of the pipe will appear at the other end of the pipe.

Execute <Ctrl-c> to stop both netcat instances.

Now, to send a HTTP request we'll need two terminal windows again. In the first we'll again be listening on port 3000:

nc -l -p 3000
But this time in the other terminal window we'll use curl to send a HTTP request to our localhost:3000 that netcat has set-up:

curl http://127.0.0.1:3000/
Now in the listening netcat terminal window simply type the following HTML code, then press <Enter> (that's important, it doesn't work otherwise) and then stop the netcat instance by executing <Ctrl-c> to see the HTML response sent back to the other terminal window where you made the initial curl request (you can do this in your browser as well if you want to see the HTML actually rendered):
