#VARIABLES
- proměnné jsou zásadní kódové struktury, které obsahují nějakou hodnotu a nějak se jmenují (mají identifikátor)
- jsou označením pro místo v paměti, kam se hodnota uloží a proměnné mají všechny programovací jazyky
> $prom = "hodnota typu string";
- $ - PHP klíčové slovo (keyword) pro vytváření proměnné
- prom - identifikátor proměnné
- "hodnota typu string" - hodnota typu string
- zásady pro tvoření identifikátorů:
	- nezapomenout na dolar
	- identifikátor může obsahovat písmena, čísla a podtržítka 
	- ale začínat může jedině písmenem nebo podtržítkem
- PHP je tzv. dynamicky/lehce typovaný jazyk, to znamená, že o proměnné nemusíme říkat, jaký typ hodnoty v sobě bude obsahovat a tento typ v ní dokonce můžeme v průběhu programu měnit
- typy hodnost (datové typy - data types):
	- String - řetězec písmen (nebo také jenom jedno písmeno), které musí být ohraničené v "" nebo ''
	- Integer - celé číslo
	- Float - desetinné číslo
	- Boolean - pravdivostní hodnota (true nebo false)
	- Array - pole homogenních prvků (jenom si myslím, že homogenních)
	- Object - instance třídy
	- NULL - nic (prázdná hodnota)
	- Resource - tento typ vrací funkce ovládající databázi (nevím přesně, co to je...)
	- Callable - funkce
- některé jazyky podporují pouze deklarování proměnné (alokace paměti, ale prozatimní neuložení hodnoty) - to PHP neumí
- funkce gettype(mixed $value): string vrátí typ $value
#CONSTANTS
- konstanty jsou proměnné, které nemohou měnit svoji hodnotu (normální proměnné měnit svou hodnotu mohou)
- v PHP se konstanty definují takto:
> define("identifikátor", "hodnota", true/false)
- define - funkce (proto ty závorky), která si bere tři argumenty a vytvoří konstantu
- "identifikátor" - identifikátor konstanty
- "hodnota" - hodnota konstanty
- true/false - boolean (proto ne uvozovky) indikátor, jestli má být identifikátor konstanty case-insensitive (true) nebo case-sensitive (false) - defaultní je false (case-sensitive)
	- true -> case-insensitive
	- false -> case-sensitive (default)
#DATA_TYPES
- o datových typech jsme se zde už bavili, ale opakování je matka moudrosti
- datové typy jsou String, Integer, Float, Array, Boolean, Object, NULL, Resource a Callable
- string je sekvence znaků obalených v "" nebo '', stringy se můžou spojovat spojovacím znakem (.)
- integer - celé číslo, které může být buď záporné (-420) nebo kladné (420), nemůže mít desetinnou čárku ani tečku, ani mezery, ani nic, kromě číslic
- float - má desetinnou tečku (4.2 nebo 6.9)
- boolean - má pouze dvě možnosti, buď true nebo false
- většina datových typů se mohou mezi sebou kombinovat (například integer a string při sčítání)
> $x = 4;
> $y = "1";
> $sum = $x + $y;
> echo $sum;
- PHP automaticky převede datový typ, na kterém se má operace vykonat (JS to taky umí, ale Python zaostává)
#VARIABLE_SCOPE
- rámec proměnné je část kódu, ve které může jistá deklarovaná proměnná použita, to záleží na místě v kódu, kde byla proměnná deklarována
- pokud byla proměnná deklarována mimo definici funkce (viz funkce), pak byla definována v globálním rámci a stala se globální proměnnou - s globální proměnnou můžou pracovat všechny části skriptu (i definice funkcí)
	- pokud ale chceme s globální proměnnou pracovat v definici funkce, musíme přidat klíčové slovo global před $identifikátor
- pokud byla proměnná deklarována uvnitř funkce, pak byla definována v lokálním rámci a stala se lokální proměnnou - s lokální proměnnou může pracovat pouze definice té funkce, která si proměnnou deklarovala, jiné části kódu ne
#VARIABLE_VARIABLES
- PHP podporuje i proměnné proměnných
- myšlenka je taková: dej proměnné hodnotu ve tvaru identifikátoru jiné proměnné a tu potom vyvolej:
> $num = 3;
> $num2 = "num";
> echo $**\$num2**; // výstup bude 3
- PHP interpreter prvně vyřeší zvýrazněnou část kódu a dosadí za ni *num*, potom uvidí $num a vypíše 3
- tímto způsobem můžeš vytvořit i proměnné proměnných proměnných
>$num = 3;
>$num2 = "num";
>$num3 = "num2";
>echo $\$\$num3; //výstup bude opět 3
- není zde limit, pokud se nepletu