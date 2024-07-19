# ejbca_ce_8.3.1
**Instllation of ejbca server with Management CA**
As the guide in the online documentation is detailed and sets you up with all you need to get started
I've spent full two weeks just to set the server up and running, since the last updates and slight change in company policy some things have been more difficult and strange. If any of you did the installation with ejbca-setup.sh script you might as well modify that script to download the newest version of wildfly and ejbca. But sice i tried to do that, I do not suggest you waste your time on it and just follow the steps for installation.

This guide will contain configuration files for EJBCA instance, it will contain cookbook with Wildfly commands with explenations and I will do my best to make you understand what is actualy happening under the hood. I used Galeon on this one, because it would be more lightweight on my system. There is not much difference except few files you would have to write yourself, but it is written in detail on PRIMEKEY page.

I suggest that you follow the guide to the letter, however in my case I will provide you with things that are needed for the EJBCA running and functioning as CA
I decided to use /opt directory as in the 
First, I would like to address the java version, java should be java 11, more accurately java-11-openjdk, make sure you export it as a system variable in profile or .bashrc of your curent user.
For my distribution which is Rocky 9 it is like this:

export JAVA_HOME=/usr/lib/jvm/java-11-openjdk 

You would have to export APPSRV_HOME variable just to make your life easier in the long run. You might add EJBCA_HOME variable just to make sure, I did as it might look for it in the process and I didnt wanna take any risks to blow my installation because of that.

I used minimal installation of the system and had to install things like ant, wget, mariadb (in my case, ejbca supports any database of your liking) etc.

And mind the selinux while you install it, installation won't be successs if you don't make tweeks on selinux, but i suggest you put it in permissive mode whille installing and later put selinux port context for ports used by ejbca 8443 8442 or if you use http proxy or firewall NAT for 443 and 80 so you can access it from the remote machine or VH. 

Wildfly console is on port 9990 and while passing commands to it it will look for localhost:9990 to access the jboss console, so you won't be able to access it via web browser from a remote machine, and i suggest you don't even think about it, because jboss cli will do everything you need for setting up the wildfly.

While i encountered persistant errors while not setting up everything correctly, I will ofcourse mention that and ways to resolve it so your mental health is better than mine.

Community is somewhat tight and it is hard to find valuable resources for error mitigation, so I will do my best to cover it. If you have any questions feel free to reach out and ask.

Good luck!




