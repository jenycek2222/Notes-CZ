`sudo dhclient -r (Windows: ipconfig /release)`
- dropne IP adresu, která byla vyžádána DHCP serverem
`sudo dhclient (Windows: ipconfig /renew)`
- vyžádá si novou IP adresu od DHCP serveru
 `which $SHELL`
 - ukáže, jakou shell používáte (/bin/bash nebo /bin/zsh nebo ...)
 `ls -l/ls -la`
 - vypíše aktuální adresář, ale u všech souborů zobrazí i vaše privilegia vzhledem k nim ve formátu rwxrwxrwx
	 - r - read (číst)
	 - w - write (zapisovat)
	 - x - execute (spouštět)
	 - s - SET UID (SUID) bit - známý PE vektor, program je spuštěn pod právem roota (asi, myslím)
- první rwx se týká toho, co může dělat aktuálně přihlášený uživatel

`ln -s zdroj link`
- vytvoří zástupce (link) na nějaký zdroj
`chsh -s cesta_k_shell_programu uživatel`
- změní výchozí shell uživateli, pokud se potom spustí CLI pod jeho jménem, spustí se právě tato shell
`passwd uživatel`
- nastaví nové heslo uživateli, prvně se samozřejmě zeptá na to staré heslo
