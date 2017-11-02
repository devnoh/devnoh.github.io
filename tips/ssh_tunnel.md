# SSH TUNNEL

## How to establish SSH Tunneling

$ ssh -fN -l your_id -i ~/.ssh/id_rsa -L local_port:172.16.0.135:27017 54.245.22.202

## Connect to remote mysql database through ssh using Java

https://stackoverflow.com/questions/1968293/connect-to-remote-mysql-database-through-ssh-using-java

My understanding is that you want to access a mysql server running on a remote machine and listening on let's say port 3306 through a SSH tunnel.

To create such a tunnel from port 1234 on your local machine to port 3306 on a remote machine using the command line ssh client, you would type the following command from your local machine:

ssh -L 1234:localhost:3306 mysql.server.remote
To do the same thing from Java, you could use JSch, a Java implementation of SSH2. From its website:

JSch allows you to connect to an sshd server and use port forwarding, X11 forwarding, file transfer, etc., and you can integrate its functionality into your own Java programs. JSch is licensed under BSD style license.
For an example, have a look at PortForwardingL.java. Once the session connected, create your JDBC connection to MySQL using something like jdbc:mysql://localhost:1234/[database] as connection URL.
