- 13. 4. 2023 - stažen obraz containeru linode/lamp, zde je dokumentace z docker hubu:
	- LAMP on Ubuntu 14.04.1 LTS Container
		- A tutorial for using this LAMP image is at:
		-   [https://www.linode.com/docs/applications/containers/linode-lamp-container-docker](https://www.linode.com/docs/applications/containers/linode-lamp-container-docker)
		Configured using the Linode "Hosting a Website" guide:
		-   [https://www.linode.com/docs/websites/hosting-a-website](https://www.linode.com/docs/websites/hosting-a-website)
	Apache Configuration:
	-   A copy of the Apache default .conf file at: **/etc/apache2/apache2.backup.conf**
	-   Changes to the Apache /etc/apache2/apache2.conf file are:
	    i. "KeepAlive Off" instead of on
	    ii. Module added to end of file:
	    iii. Hostname added to end of file: **ServerName localhost**
	-   Enabled Virtual Host file at /etc/apache2/sites-available/example.com.conf
	-   Created directories for Virtual Host file:
	    /var/www/example.com /var/www/example.com/public_html /var/www/example.com/log /var/www/example.com/backups
	MySQL Configuration:
	-   Temporary root password: "Admin2015" Change immediately!
	-   Ran mysql_secure_installation : i. Removed anonymous user accounts ii. Disable remote root login iii. Removed the test database
	-   MySQL configuration file at /etc/mysql/my.cnf i. Changed settings: max_connections = 75 key_buffer = 32M max_allowed_packet = 1M thread_stack = 128K table_cache = 32
	-   Example database: exampleDB
	-   Example user: example_user
	-   Example user password: Admin2015
	PHP Configuration:
	-   PHP configuration file at /etc/php5/apache2/php.ini
	    i. Changed settings: max_execution_time = 30 memory_limit = 128M error_reporting = E_COMPILE_ERROR|E_RECOVERABLE_ERROR|E_ERROR|E_CORE_ERROR display_errors = Off log_errors = On error_log = /var/log/php/error.log register_globals = Off
	-   Created directory: /var/log/php
	-   Changed /var/log/php ownership to www-dat
- 13. 4. 2023 - spušten container pomocí tohoto příkazu:
	- docker run -p 80:80 -t -i --mount src="D:/DockerVolumes/LAMP/WebContent",target=/var/www/example.com/public_html,type=bind --mount src="D:/DockerVolumes/LAMP\Logs",target=/var/www/example.com/log,type=bind --mount src="D:/DockerVolumes/LAMP/Backups",target=/var/www/example.com/backups,type=bind linode/lamp /bin/bash
- 13. 4. 2023 - container přejmenován ze serene_poitras na LAMP