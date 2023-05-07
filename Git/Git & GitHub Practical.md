- Git repozitář může být na počítači vytvořen pomocí příkazu *git init*
- pokud chceme lokální git repozitář nahrát na GitHub, musíme na GitHubu nejprve vytvořit nový prázdný repozitář
	- Tvoje logo účtu -> Your repositories -> New
- Následně musíme na lokálním PC vybrat to, co budeme dávat na GitHub pomocí příkazu *git add .*, ten přidá všechny soubory v našem aktuálním adresáři
- potom pomocí příkazu *git commit -m "popis_commitu"* vytvoříme verzi našeho adresáře
- potom nastavíme přihlašovací údaje na GitHub, spojíme tak Git a GitHub
	- *git config --global user.name "jenycek2222"*
	- *git config --global user.email "jendanovak05@gmail.com"*
- potom se připojíme ke GitHubu příkazem *git remote add origin "odkaz_k_repozitáři"*
- a protlačíme změny na GitHub repozitář: *git push -u origin main*

- chtěl jsem nahrát repozitář z mobilu na platformě termux, podstoupil jsem stejné kroky, ale ještě před *git add .* jsem zadal *git config --global --add safe.directory /storage/emulated/0/Download/GitHubWorkspace/Notes-CZ*, jinak to házelo error
- u git push je shell výstup trochu jiný, asi to bude rozdílnými verzemi gitu, na mobilu tam musíš zadat své uživatelské jméno a PAT, který je uložen v souboru H.txt
# Co udělat před každým pushem?
- Windows:
	- git add .
	- git commit -m "nazev_commitu"
	- git push -u origin main
- Termux:
	- git add .
	- git commit -m "nazev_commitu"
	- git push -u origin main
		- zadat jenycek2222 a ten PAT