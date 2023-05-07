- kontrolní struktury dávají kódu možnost provádět komplikovanější úkoly rychleji a automatzovaně, dávají programu možnost rozhodnout se
- kontrolní struktury mohou spustit jiný kód v závislosti na tom, jaký vstup uživatel zadá
#CONDITIONAL_STATEMENTS
- podmínkové výroky spustí jeden blok kódu, pokud je specifikovaná podmínka pravdivá (if), druhý blok kódu, pokud je specifikovaná podmínka nepravdivá (else), a popříadě další bloky kódu, pokud jsou specifikovány další podmínky (elseif)
- syntaxe pro podmínkový výrok je následující:
>if (*podmínka*) {
>	//kód, který proběhne, je-li *podmínka* pravdivá
>} elseif (*jiná_podmínka*) {
>	//kód, který proběhne, je-li *podmínka* nepravdivá a *jiná_podmínka* je pravdivá 
>} else {
>	//kód, který proběhne, není-li ani jedna podmínka pravdivá 
>}
- konkrétní příklad:
>$age = 21;
>if ($age < 13) {
>	echo "Child";
>} elseif ($age <20) {
>	echo "Teenager";
>} else {
>	echo "Adult";
>}
>//bude vypsáno adult
- podmínka v elseif bude vyhodnocována pouze tehdy, pokud podmínka v řídícím if bude nepravdivá, proto jsme u teenagera nemuseli specifikovat, že věk musí být většínež 13
- pokud bychom ale místo elseif použili if, PHP by to vnímal jako začátek nového podmínkového výrazu, takže při stejné podmínce ($age<20), by se například u věku 8 zobrazilo jak Child, tak Teenager
- proto bychom při použití dvou if měli uvést konkrétnější podmínku:
>$age = 8;
>if ($age < 13) {
>	echo "Child";
>} if ($age >= 13 and $age <20) {
>	echo "Teenager";
>} else {
>	echo "Adult";
>}
>//bude vypsáno pouze Child

#THE_WHILE_LOOP
- někdy se nám může hodit běže stejný kus kódu vícekrát za sebou, pro tento účel byla vymyšlena while-loop (dokud-smyčka)
- while-loop spouští kód, dokud je specifikovaná podmínka pravdivá 
- v podmínce většinou figuruje proměnná, která se v bloku kódu while-loopu mění, aby se někdy stala podmínka nepravdivou a while smyčka byla ukončena (jinak by byla nekonečná)
- nekonečné while-smyčky se nedoporučuje používat, ale občas se hodí (pokud chceme vytvořit nekonečnou while-smyčku, za *podínku* dosadíme true)
- syntaxe:
> while (*podmínka*) {
>	//kód, který je spuštěn, je-li podmínka pravdivá
>	//výrok, který přiblíží kontrolní proměnnou blíže k neplatnosti podmínky
> }
- konkrétní příklad (odpočet):
> $i = 10;
> while ($i >= 0) {
>	echo "Starting in: ".$i." s<br />";
>	$i--;
> }

#THE_DO_WHILE_LOOP
- funguje podobně jako while-smyčka, ale podmínku kontroluje až po spuštění kódu v smyčkovém bloku
- syntaxe:
>do {
>	//kód, který má být proveden
>	//výrok, který přiblíží kontrolní proměnnou blíže k neplatnosti podmínky
>} while (*podmínka*);
- kód v smyčkovém bloku bude proveden vždy alespoň jednou, protože se podmínka kontroluje až po jeho provedení 