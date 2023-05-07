`ipconfig`
- zobrazí základní informace o jednotlivých rozhraních (IPv4/6 adresa, výchozí brána, maska podsítě)
`ipconfig /all`
- zobrazí veškeré informace o jednotlivých síťových rozhraních (IPv4/6 adresa, výchozí brána, maska podsítě, MAC adresa, čas expirace DHCP odpovědi, DNS servery, popisek, ...)
`ipconfig /all | findstr DNS`
- | - symbol trubky (pipe), informace z prvního příkazu (ipconfig /all) předá druhému příkazu (findstr DNS)
- findstr vyhledá a vypíšez  předaných informací z předchozího příkazu jen ty řádky, které obsahují slovo DNS
`ipconfig /release "rozhraní"`
- vypustí starou IP adresu na všech rozhraních, tím pádem se všechny ocitnou bez ní
- pokud je rozhraní nastaveno na statickou IP adresu, nebude mu příkaz mazat IP adresu
- možno v uvozovkách "" specifikovat i název rozhraní, kterého se má příkaz týkat
`ipconfig /renew`
- vyžádá si od DHCP serveru novou IP adresu pro všechny rozhraní, které DHCP servis mají zapnutý
- pokud rozhraní DHCP servisy nepoužívá, nezíská IP adresu
- možno v uvozovkách "" specifikovat i název rozhraní, kterého se má příkaz týkat
`ipconfig /displaydns`
- zobrazí všechny servery, ke kterým zná PC doménová jména
- zobrazí také extra informace o každém DNS záznamu
`<předchozí příkaz> | clip`
- umístí výstup předchozího příkazu do schránky (clipboard - Ctrl + V)
`ipconfig /flushdns`
- vymaže všechny uložené DNS záznamy
`nslookup <doménové jméno>`
- udělá záznam pro zadané doménové jméno a zobrazí ho
`cls`
- vyčístí obrazovku a přemístí prompt úplně nahoru
`getmac /v`
- zobrazí MAC adresy všech rozhraní
`powercfg /energy`
- zobrazí informace o problémech nebo chybách v dodávání energie ze sítě - uloží ho do html souboru
`powercfg /batteryreport`
- zobrazí stav baterie - uloží ho do html souboru
`assoc <přípona>=<program>`
- zobrazí, jaké přípony souborů jsou přiřazeny jakým programům k automatickému otevření
- při volitelném předání zadaných argumentů se tyto informace nezobrazí, nýbrž se konkrétní přípona přenastaví
`chkdsk`
- `/f` - s tímto přepínačem projde checkdisk diskem a opraví nalezené chyby
- `/r` - s tímto přepínačem projde checkdisk chyby fyzických sektorů a opraví je
- pravěpodobně bude potřebovat restartování PC
`sfc /scannow`
- system file checker - zkontroluje souborové soubory a opraví poškozené
`DISM`
- Deployment Image Servicing and Management - opraví souborový obraz disku (ISO)
- `/Online /Cleanup /CheckHealth` - tyto přepínače je dobré použít na takovou kontrolu
- `/Online /Cleanup /ScanHealth` - tyto přepínače se používají na trochu delší, ale efektivnější scan
- `/Online /Cleanup /RestoreHealth` - tyto přepínače se používají na opravení disku
- po těchto DISM příkazech je dobré znovu spustit sfc
`tasklist`
- zobrazí všechny procesy běžící na našem PC
`taskkill /f /pid <ID procesu>`
- na základě daného ID procesu ukončí proces
`netsh wlan show wlanreport`
- podá cool a fancy report o připojení k WLAN
`netsh advfirewall set allprofiles state off/on`
- vypne nebo zapne firewall
`netsh interface show interface`
- zobrazí síťová rozhraní na PC
- netsh dokáže mnohem víc, ale tohle je jenom základ
`ping <server>`
- vyšle ICMP echo request na specifikovaný server (v základu 4x)
- `/t` - bude vysílat zprávy pořád
`tracert <server>`
- vypíše, přes které všechny routery paket šel k cílovém zadanému serveru a vypíše i odezvu od těchto tzv. hopů
- `/d` - nebude luštit doménová jména hopů a bude tak rychlejší
`netstat`
- řekne ti, k jakým serverům jsi připojen a jaké jsou naopak připojeny k tobě
- `/af` - zobrazí otevřené porty
- `/o` - zobrazí s připojeními i názvy procesů, ke kterým se připojení váže, takže tato připojení můžete terminovat ukončením procesu
- `/e /t 5` - každých pět sekund zobrazí informace o přijatých a odeslaných paketech
`route print`
- zobrazí routing table PC (kam PC vyšle pakety, které spadají do určitého síťového místa) - typické je vidět tam default route směřující na default gateway
`route add`
- přidá route do routing tabulky - můžeme editovat i default route
`route delete`
- smaže route z tabulky - pokud jsi zadal více default routů, tak na smazání jednoho konkrétního pouze zadej více určujících informací
`shutdown`
- vypne PC
- `/r /fw /f /t 0` - počítač se restartuje a naběhne do BIOSu
- `netplwiz` - zobrazí gui obsahující všechny uživatele na PC