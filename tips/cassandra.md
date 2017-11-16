# CASSANDRA


Installing Cassandra on Mac OS X
================================

Install Homebrew
----------------
Homebrew is a great little package manager for OS X. If you haven't already, installing it is pretty easy:
```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

Install Python
--------------
Mac OS X has a copy of Python preinstalled, but this makes sure you get the newest version.
```
brew install python
```

Install cql
-----------
To use cqlsh, the Cassandra query language shell, you need to install cql:
```
pip install cql
pip install cassandra-driver
```

Install Cassandra
-----------------
This installs Apache Cassandra:
```
brew install cassandra
```

Starting Cassandra
------------------
At the end of the install, brew will tell you about two ways to launch Cassandra. The first will launch it when the computer restarts, but this isn't recommended because you may not want to always run Cassandra. Instead use this command:
```
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.cassandra.plist
```
Or even easier:
```
launchctl start homebrew.mxcl.cassandra
```
and to stop:
```
launchctl stop homebrew.mxcl.cassandra
```

On Mavericks, Homebrew failed to move the plist file into LaunchAgents. Which gives this error message:
```
launchctl: Couldn't stat("/Users/MNCH/Library/LaunchAgents/homebrew.mxcl.cassandra.plist"): No such file or directory
```

To fix this just issue the following command. Then, try using the ```launchctl load``` command again:
```
cp /usr/local/Cellar/cassandra/2.1.2/homebrew.mxcl.cassandra.plist ~/Library/LaunchAgents/
```

Cassandra file locations
------------------------
Properties: /usr/local/etc/cassandra  
Logs: /usr/local/var/log/cassandra  
Data: /usr/local/var/lib/cassandra/data  

Finally cqlsh should connect to cassandra:
------------------------------------------
```
$> cqlsh
Connected to Test Cluster at 127.0.0.1:9042.
[cqlsh 5.0.1 | Cassandra 2.1.2 | CQL spec 3.2.0 | Native protocol v3]
Use HELP for help.
cqlsh>
cqlsh>
```

Have fun with Cassandra!
