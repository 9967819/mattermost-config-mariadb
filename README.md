# mattermost-config-mariadb
Working configuration for running Mattermost 8 with MariaDB 10. 


### Initial requirements

	1. Updated GNU/Linux operating system. 
	2. MariaDB 10.11.xx (LTS) server (apt-get install mariadb-server)

This config has been tested with Rocky Linux 9.2 and Debian based systems using precompiled binaries.
To upgrade the base system :

	% apt-get update && apt-get upgrade

### Mattermost install 

	1. Create the /home/mattermost directory 

	2. Create the mattermost user and group

		# adduser mattermost
		# groupadd mattermost

	3. Copy and edit mattermost/config.json to /home/mattermost/config/ 

	4. Initialize mattermost database 

		mysql> create database mattermost;

	5. Setup standard mmuser rights

		mysql> grant privileges ....
		mysql> flush privileges

### NGINX configuration (reverse nginx proxy)

1. Copy nginx/mattermost.conf to /etc/nginx/conf.d/

	% sudo cp nginx/mattermost.conf /etc/nginx/conf.d/

### Mattermost advanced tuning 

	...

### MariaDB setup 

	...

### systemd configuration

	% sudo cp systemd/mattermost.service /usr/lib/systemd/system/
	% sudo systemctl enable mattermost 
	% sudo systemctl start mattermost 

### Final notes 

Dear Mattermost developers, MariaDB is a fully backward-compatible MySQL server derivative!! There is absolutely no harm in using MariaDB with Mattermost on Linux. Please stop giving a bad name to MariaDB, thank you! :-)

