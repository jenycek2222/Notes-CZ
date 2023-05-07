> Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
- pokud jako uživatel budeš mít někdy práva na to měnit ostatním uživatelům hesla, takhle to uděláš
> Rename-Computer *nové_jméno*
- přejmenuje počítač (hostname)
> Get-Service *pattern*
- zobrazí všechny spustitelné servisy, podle patternu (* pro všechny)
> Start-Service *service_name*
- spustí servis *service_name*
>Set-Service -Name *service_name* -StartupType 'Automatic'
- nastaví servis *service_name*, aby se spouštěl automaticky (hodí se na ssh)
# NETWORKING
>Resolve-DNSName
- podobné jako dig příkaz na Linuxu, vyhledá DNS záznam v DNS serveru
>Test-NetConnection *IP_adresa* -Port *port*
- zkusí se připojit k *IP_adrese* na portu *port*
- ukázkový výstup:
	- ![[Pasted image 20230506085315.png]]
> 