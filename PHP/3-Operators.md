#ARITHMETIC_OPERATORS
- aritmetické operátory fungují na číselných hodnotách a provádějí s nimi aritmetické operace
- v PHP máme tyto aritmetické operátory:
	- + (sčítání) - nefunguje na stringy
	- - (odčítání)
	- * (násobení)
	- / (dělení)
	- % (modulo)
	- . (spojování stringů - konkatenace) - výjimka, neprobíhá na číselných hodnotách
	- post decrement, post increment, pre decrement, pre increment
- modulo (%) - vrací zbytek při dělení dvou integerů (5 % 3 == 2)
	- pokud jeden z operandů je float, tak ho PHP převede na int
- post/pre decrement/increment (\$x++, \$x--, ++\$x, --\$x)
	- všechny tyto 4 operace se používají na přidání (increment) nebo odebrání (decrement) hodnoty 1 od/do integeru
	- rozdíl mezi post a pre je ten, že post modifikuje proměnnou až po jejím **případném** použítí, ale pre ji modifikuje už předtím (viz kód)
	> $a = 2;
	> $b = $a++;  // \$b = 2, $a = 3
	> $a = 2;
	> $b = ++\$a;  // $b = 3, $a = 3
	> $a++;  // \$a = 4 nemusíme nutně používat dvě hodnoty,
	>            // stačí jedna...
- podle počtu operandů rozdělujeme aritmetické operace na unární, binární, ternární, ...
#ASSIGNMENT_OPERATORS
- přiřazovací operátory se používají k přiřazení hodnoty do proměnné
- PHP podporuje tyto přiřazovací operátory:
	- $x = $y (klasické rovná se - proměnné x je přiřazena hodnota uložená v proměnné y)
	- $x += $y (stejné jako $x = $x + $y)
	- $x -= $y (stejné jako $x = $x - $y)
	- $x \*= $y (stejné jako $x = $x * $y)
	- $x /= $y (stejné jako $x = $x / $y)
	- $x %= $y (stejné jako $x = $x % $y)
	- $x .= $y (stejné jako $x = $x . $y)
#COMPARISON_OPERATORS
- porovnávací operátory vytváří tzv. logický výraz, který PHP interpreter vyhodnotí buď jako true nebo false
- PHP podporuje tyto porovnávací operátory:
	- $x == $y - rovná se - pokud jsou hodnoty $x a $y stejné, bude výraz pravdivý (5 == 5 ... true, 5 == 5.0 ... true)
	- $x != $y nebo \$x <> \$y - nerovná se - pokud se hodnoty nerovnají (nejsou stejné), bude výraz pravdivý (5 != 5 ... false, 5 != 5.0 ... false)
	- $x === $y - je identické s - pokud jsou si hodnoty identické (mají stejnou hodnotu i typ), bude výraz pravdivý (5 == 5 ... true, 5 == 5.0 ... false)
	- $x !== $y - není identické s - pokud si hodnoty nejsou identické (mají jinou hodnotu nebo jiný typ), bude výraz pravdivý (5 !== 5 ... false, 5 !== 6 ... true, 5 !== 5.0 ... true)
	- $x > $y - je větší než - pokud má $x větší hodnotu než $y, bude výraz pravdivý
	- $x >= $y - je větší nebo rovno - pokud má $x větší nebo stejnou hodnotu s $y, bude výraz pravdivý 
	- $x < $y - je menší než - pokud má $x menší hodnotu než y, bude výraz pravdivý 
	- $x <= $y - je menší nebo rovno - pokud má $x menší nebo stejnou hodnotu jako $y, bude výraz pravdivý 
#LOGICAL_OPERATORS
- logické operátory spojují porovnávací operátory (nebo i další logické pomocí závorek), přičemž jsou opět vyhodnoceny jako true/false
- PHP rozlišuje tyto logické operátory:
	- $st1 and $st2 - konjunkce (a) - pokud jsou první výrok (statement) a druhý výrok oba pravdivé, potom je celý výrok pravdivý
	- $st1 or $st2 - disjunkce (nebo) - pokud je alespoň jeden z výroků pravdivý (klíďo i oba), potom je celý výrok pravdivý
	- $st1 xor $st2 - exkluzivní disjunkce (buď anebo) - pokud je právě jeden výrok pravdivý (ne oba), potom je celý výrok pravdivý
	- $st1 && $st2 - ekvivalentní s $st1 and $st2
	- $st1 || $st2 - ekvivalentní s $st1 or $st2
	- !$st1 - negace - vratí true pouze pokud $st1 je false
#BITWISE_OPERATORS
- v sololearnu to nemaj


