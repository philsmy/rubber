The rubber plugin enables relatively complex multi-instance deployments of
RubyOnRails applications to Amazon's Elastic Compute Cloud (EC2).

See the documentation in the github wiki for more details:
http://github.com/rubber/rubber/wiki

While most things work, there is still an issue with initializing the mysql database.
During bootstrapping you'll get an error with mysql.

You'll need to do:
sudo mysqld --initialize --user=mysql --datadir=/mnt/mysql/data

In the output of this will be your temporary root password.
Log in to mysql with that and then set it to a real password. I use this to do that:

SET PASSWORD = PASSWORD('myAmazingPassword');

Another thing to note is that if you don't set a password for your rails user to get to the database the creation of things won't work (of course you should have a password anyway!)

[![Build Status](https://secure.travis-ci.org/rubber/rubber.png)](http://travis-ci.org/rubber/rubber)
