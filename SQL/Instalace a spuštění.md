Nainstaloval jsem to na WSL Ubuntu: sudo apt install mysql-server -y

Důležité je zkontrolovat, jestli proces mysql (démon) běží: sudo service mysql status (na wsl nefunguje systemctl) - pokud neběží, tak spustit: sudo service mysql start

MySQL lze spustit příkazem: sudo mysql



ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2) - tento error je způsoben nespuštěným mysql démonem


Docker MySQL login:
	1. mysql -u root -p
	2. *Enter your password:* megamysl
