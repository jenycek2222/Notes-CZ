#INTRODUCTION_TO_ARRAYS
- pole (array) je datový typ, který ukládá více hodnot zároveň, hodí se na dlouhé seznamy (jmen, nákupu, ...)
- pokud budeme chtít uložit 50 jmen pomocí proměnných, budeme potřebovat 50 zdlouhavých řádků kódu:
> $name1 = "David";
> $name2 = "John";
> $name3 = "George";
>... 
- použijeme-li ale pole, bude syntaxe vypadat takto:
> $names = array("David", "John", "George", ...);
- použití polí je daleko efektivnější a více škálovatelné, chceme-li vytvořit dlouhé seznamy
#NUMERIC_ARRAYS
- numerická/indexovaná (numeric/indexed) pole jsou pole, k jejichž obsahu přistupujeme pomocí indexu, který byl jednotlivým prvkům pole přiřazen při jejich vytvoření
- náš seznam jmen je příkladem. numerického pole
- při použití syntaxe $array_name = array(prvek1, prvek2, prvek3); je. prvkům 1-3 automaticky přiřazen index 0-2, takže prvek1 má index 0, ..., ano počítá se to od nuly
- jeden index může odkazovat pouze na jeden prvek pole
- ručně můžeme prvku v arrayi přiřadit index takto:
> $arr = array(); //vytvoření prázdného arraye
> $arr[0] = "David" //manuálně jsme na index 0 umístili string "David"
> $arr[1] = 5 //manuálně jsme na index 1 umístili číslo 5 (žije) (short circuit)
- pokud budeme chtít přistoupit k nějakému prvku z numerického arraye, musíme k tomu použít jeho index:
	- echo $arr[0]; //vypíše prvek s indexem 0 (první prvek)
- pokud budeme chtít přistoupit k prvku pomocí nedefinovaného indexu, dostaneme chybové hlášení
- jeden array může obsahovat více datových typů najednou (array může být heterogenní)
#ASSOCIATIVE_ARRAYS
- asociativní pole se chovají podobně jako ta numerická, avšak namísto indexů používají klíče
- jeden klíč může odkazovat pouze na jeden prvek asociativního pole
- při deklaraci asociativního pole musíme explicitně deklarovat každý klíč, protože narozdíl od indexů zde není žádná pravidelnost (řada) při jejich tvoření
- vytvoření asociativního arraye:
> $a_arr = array("mother" =\> "Diana", "father" =\> "Robert"); //první způsob (vždy používáme syntaxi klíč=\>hodnota)
> $a_arr["son"] = "John"; //druhý způsob
- k uloženým hodnotám přistupujeme pomocí klíče, ne indexu
>echo $a_arr["father"]; //vypíše Robert do HTML dokumentu
- numerická pole jsou speciálním typem asociativních polí, která mají číselné hodnoty jako klíče
- deklarace numerického pole pomocí asociativní syntaxe:
> $n_arr = array(0 =\> "first", 1 =\> "second");

#MULTI-DIMENSIONAL_ARRAYS
- vícerozměrná pole jsou pole, která obsahují další pole
- 2-D pole je pole obsahující 1-D pole (normální pole)
- n-D pole je pole obsahující (n-1)-D pole
- syntaxe pro definici 2-D pole:
>$md_arr = array(array(1, 2, 3), array(4, 5, 6), array(7, 8, 9)); //2-D array, který obsahuje 3 1-D arraye
- pokud chceme přistoupit k jednotlivých prvkům 1-D polí, použijeme tuto syntaxi:
>echo $md_arr\[0]\[1]; //bude vypsáno číslo 2
- PHP interpreter při běžení kódu prvně uvidí $md_arr[0], uvědomí si, že je to array(1, 2, 3), tak čte dál, až uvidí [1], tím pádem nakonec vypíše druhou hodnotu z prvního arraye 2-D arraye
- vícerozměrná pole se dají připodobnit k proměnné proměnných v tom smyslu, že PHP prvně vyřeší jednu část výrazu, tu "vyčíslí" a potom se přesune k další části výrazu
- $md_arr by se dal také zapsat pomocí této tabulky:
	- 1	2	3
	- 4	5	6 
	- 7	8	9
- parametr v první závorce by potom určoval pozici na ose y, parametr v druhé závorce pozici na ose x
- $md_arr by se ale dal také zapsat pomocí takovéto tabulky:
	- 1	4	7
	- 2	5	8
	- 3	6	9
- u této tabulky by parametr v první závorce určoval pozici na ose x a parametr v druhé závorce pozici na ose y
- můžeme mít i 3-D array, i 4-D array, není zde limit, ale tabulkou lze vyjádřit pouze 2-D array, na 3-D array bychom potřebovali trojrozměrnou soustavu... 
- můžeme také kombinovat numerická a asociativní pole - můžeme mít numerická pole v asociativních atd. 
#ADVANCED_ARRAYS
- pokud chceš zobrazit celý docela pěkně formátovaný array, použij tuto syntaxi:
	- print_r($array_name);