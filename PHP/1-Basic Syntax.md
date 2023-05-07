#INTRODUCTION_TO_PHP
- PHP (Personal Home Page/Hypertext Preprocessor) je skriptovací jazyk využívaný k vývoji pokročilých webových stránek
- PHP scripty běží na serveru (server-side)
- Wordpress a Facebook jsou založeny na PHP jádře
- PHP je kompatibilní se všemi moderními webovými serverovými programy (Apache, IIS, ...)
- PHP scripty vracejí po interpretaci HTML text, který je zobrazen v prohlížeči
#PHP_TAGS
- PHP se vkládá do HTML dokumentu pomocí tří možných značek:
	- <?php kód... ?> - nejlepší a nejpodporovanější cesta
	- <script language="php"> kód... </script> - PHP 7 už nepodporuje tento způsob zápisu
	- <? kód... ?> - tuto syntaxi už některé servery také nepodporují
#ECHO
- echo je příkaz, který se používá k poslání výstupu do webové stránky
- není to funkce, ale jazykový konstrukt (language construct) a tak nepotřebuje závorky
> echo "<p>nějaký text</p>";
- užívaný text by měl vždy být v "" nebo ''
- každý PHP příkaz musí končit středníkem (;)
- v příkazu echo můžeme používat normální HTML syntaxi
#COMMENTS
- jako každý jazyk, i PHP má komentáře, které slouží k tomu, aby člověk, který tvůj kód čte (někdo jiný nebo klidně i ty) rozuměl tomu, co chtěl básník říci
- komentáře jsou interpreterem ignorovány
- zde je příklad komentáře na jeden řádek (ten přestane platit, pokud interpreter rozpozná konec řádku (\\n) nebo konec php srciptu (?>))
> echo "Ahoj Světe!"; // tento řádek napíše Ahoj Světe! 
- komentář na více řádků také v PHP existuje
> /*
> toto je víceřádkový
> komentář
> \*/