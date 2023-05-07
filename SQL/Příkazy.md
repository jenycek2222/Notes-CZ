každý příkaz musí končit středníkem ;
sloupec (column=field)
řádek (row=record)
SQL je case insensitive (SELECT=seleCt)

> show databases;
- zobrazí všechny databáze
> create database __database_name__;
- vytvoří databázi (jméno může obsahovat čárky i háčky)
> use __database_name__;
- vybere databázi, se kterou budete potom moci manipulovat
> show tables;
- vypíše všechny tabulky v databázi
> create table __table_name__ (
	-> __first_column__ __data_type__,
	-> __second_column__ __data_type__,
	-> __third_column__ __data_type__,
	-> __last_column__ __data_type__,
	-> PRIMARY KEY (__column_name__)
	-> );
- vytvoří tabulku o několika sloupcích (column), které musí mít stejný datový typ (možnosti: int, varchar (variable character), boolean=tinyint(1))
- sem se dá přidat i volba sloupce, který bude figurovat jako primární klíč
> drop table/database __table_name__;
- odstraní specifikovanou tabulku/databázi 
> describe __table_name__;
> show columns from __table_name__;
- vypíše sloupce v dané tabulce (schéma tabulky - schema) - obě možnosti fungují naprosto stejně
- sloupec Key ve výstupu zobrazuje typ sloupců (které jsou napsány tentokrát v řádcích) - PRI znamená primární klíč
> insert into __table_name__ (__first_column__, __second_column__, __third_column__, ...) values (__first_attribute__,  __second_attribute__, __third_attribute__, ...);
- vloží do tabulky právě jeden řádek, do druhé závorky se píšou atributy, kterých musí být stejný počet jako specifikace sloupců v první závorce
- specifikace sloupců je ale nepovinná, nepoužijeme-li ji, musíme dbát, abychom atributy vkládali ve stejném pořadí, jako byly definovány
> select __column__, __another_column__ from __table_name__ where __column_name__=__value__ or/and/xor __column_name__=__another_value__;
- vybere daný řádek/dané řádky (oddělují se čárkou)/vše (* ) z dané tabulky a zobrazí je, popřípadě i vyfiltruje pomocí příkazu where ...
- vybraná data jsou také ve formátu tabulky (výsledné tabulky), která se jmenuje result-set
> delete from __table_name__ where __column_name__=__value__;
- z tabulky odstraní řádky podle filtru, který má za úkol specifikovat určitou skupinu lidí, bez něj by se odstranilo vše
> update __table_name__ set __column_name__=__updated_value__ where __column_name__=__value__;
- určitou hodnotu v tabulce (která je opět specifikována filtrem) přepíše na novou hodnotu (updated value)
> select __column_name__ from __table_name__ order by __column_name__ asc/desc, __another_column_name__ asc/desc;
- seřadí výstup podle daného sloupce buď vzestupně (asc - ascending) nebo sestupně (desc - descending), pokud není specifikováno, používá se asc
- lze použít i více seřaďovacích sloupců, pokud by tedy první sloupec v případě některých řádků nerozhodl (řádky by byly stejné), tak by se přešlo na druhý sloupec
> *alter table* __table_name__ *add* __column_name__ __data_type__;
- přidá do tabulky sloupec určitého datového typu
> select *distinct* __column_names__ from __table_name__;
- vybere pouze unikátní řádky podle toho, jestli se v __column_names__ (může být jedna i více - oddělovat čárkou) opakují, zbytek nevypisuje
> select __columns__ from __table_name__ *limit* __number__ *offset* __another_number__;
> select __columns__ from __table_name__ *limit* __another_number__ __number__;
- příkaz limit je doprovázen číslem za ním, které říká, kolik záznamů se má vypsat
- příkaz offset je doprovázen jiným číslem, které říká, kolik záznamů má příkaz limit na začátku přeskočit
- druhý příkaz je zkrácenou formou toho prvního, chová se ale stejně
> select __columns__ from __table_name__ where __column_name__ *between* __value1__ *and* __value2__;
> select __columns__ from __table_name__ where __column_name__ >= __value1__ and <= __value2__;
- příkaz between ... and se používá s příkazem where na vytvoření jakési škály čísel, která se poté uplatní při filtrování
- spodní i horní hranice jsou obě započítány do škály
- první a druhý příkaz jsou ekvivalentní
> select __columns__ from __table_name__ where __column_name__ *in (__first_value__, __second_value__, __third_value__, ...)*;
> select __columns__ from __table_name__ where __column_name__ = __first_value__ or __column_name__ = __second_value__ or __column_name__ = __third_value__ or ...;
- příkaz in se používá, když chceme jednodušeji vyfiltrovat tabulku podle několikerých argumentů v jednom sloupci
- první a druhý příkaz jsou ekvivalentní
- opak potom dělá not in příkaz
- in = whitelist
- not in = blacklist
> select *concat (__column_name__, ", ", __another_column_name__) as __concat_column_name__* from __table_name__;
- příkaz concat vypíše z každého řádku spojené hodnoty, které jsme mu zadali na spojení, je to jako tabulka, ale docela jiný formát, v hlavičce tabulky se ukáže concat (__column_name__, ", ", __another_column_name__)
- avšak pokud za příkazem concat použijeme příkaz as, tak se v hlavičce vypsané concat tabulky ukáže __concat_column_name__
> select __column_name__ as __custom_column_name__, __another_column_name__ as __another_custom_column_name__ from __table_name__;
- příkaz as se dá použít i na přejmenování normálních sloupců, ne jenom concat sloupce
> select __column_name__, *upper(__another_column_name__), lower (__one_more_column_name__)* from __table_name__;
- funkce upper a lower zařídí, že všechny písmena v daném sloupci budou buď malá (lower()) nebo naopak velká (upper()), pokud ovšem nechceme, aby příkaz select vytiskl v hlavičce doslova upper(__column_name__), použijeme příkaz as (upper(__column_name__) as __column_name__))
- na čísla nemají tyto funkce žádný vliv
> select *sqrt(__column_name__), power(__another_column_name__, __exponent__)* from __table_name__;
> select *avg(__column_name__), sum(__another_column_name__), min(__another_column_name__), max (__one_more_column_name__)* from __table_name__;
- toto jsou matematické funkce, které se dají uplatnit pouze na sloupce s čísly, pokud použijete matematickou funkci na písmena, vypíše to nulu a za každý řádek to připíše jedničku do varování (__x__ warnings)
- sqrt = odmocní číslo v každém řádku daného sloupce, power = umocní číslo v každém řádku daného sloupce na daný exponent, avg = vypíše průměr, sum = vypíše sumu, min = vypíše nejmenší hodnotu, max = vypíše největší hodnotu
- v horní query jsou příkazy, které vypíší určitou hodnotu pro každý řádek, ale v dolní query se vždy vypíše pouze jeden řádek, který je podle selského rozumu samozřejmě společný pro všechny, pokud budete v jedné query kombinovat tyto dva druhy matematických funkcí, vyhodí vám to error, protože jsou nekompatibilní
> select __columns__ from __table_name__ where __column_name__ *like __pattern__*;
- regulární exprese v SQL se dají dělat pomocí příkazu like
- %A pattern vybere všechna slova, která končí na A nebo a, protože SQL je case insensitive
- \_A pattern vybere všechna slova, která mají druhé písmeno A nebo a 
- %\[asd\] pattern vybere všechna slova, která končí na a, s nebo d
- %\[a-z\] pattern vybere všechna slova, která končí na jakékoliv písmeno (a až z)
- % - znamená 0 nebo více znaků, \_ znamená přesně jeden znak, \[\] znamená skupinu znaků v disjunkci (ten nebo ten znak...)
> select __columns__ from __table_name__ where __a_column_name__ > *(select avg(__a_column_name__) from __table_name__)*;
- subqueries jsou celé příkazy uvnitř příkazů, vždy se vkládají do závorky a fungují tak nějak jako funkce v pythonu, vždy vrátí nějakou hodnotu, kterou potom použije query, která ji vyvolala
- ukázka použití: chcete vybrat z tabulky zaměstnanců pouze lidi, jejichž plat je vyšší než průměr a seřadit je podle velikosti od největšího platu po nejnižší, uděláte to takto:
> select first_name, last_name, salary from employees where salary > (select avg(salary) from employees) order by salary desc;
- subquery se neukončuje středníkem, ale musí být ohraničena kulatými závorkami
> select __table_name__.__column_name__, __other_table_name__.__other_column_name__ from __table_name__, __other_table_name__ where __table_name__.__joining_column_name__=__other_table_name__.__other_joining_column_name__;
- joinování tabulek je způsob, jak spojit data ze dvou a více tabulek, tyto data se potom vytisknou do prozatimní (temporary) tabulky, která se nikde neukládá a dá se vypsat pouze příkazem
- základem joinování jsou plně kvalifikovaná jména (Fully Qualified Names), která upřesňují, z jaké tabulky pochází daný sloupec, píšou se ve formátu __table_name__.__column_name__, což znamená, že __column_name__ se dá najít v tabulce __table_name__
- všimněme si, že při joinování tabulek referujeme k více tabulkám u příkazu from, to právě kvůli podstatě joinování (spojení dvou a více tabulek do jedné temporární)
- důležité je synchronizovat pořadí tabulek pomocí jednoho řádku z každé tabulky, nejlepší je pro tento účel vybrat sloupce, které budou mít společné hodnoty (customer.id - id zákazníka v tabulce customer, purchases.customer_id - id zákazníka, který si něco koupil) - synchronizaci provedeme příkazem where, který spojí rovnítkem tyto dva vybrané kompatibilní sloupce
> select __short__.__column_name__, __another_short__.__column_name__ from __table_name__ as __short__, __another_table_name__ as __another_short__ where __short__.__column_name__=__another_short__.__column_name__;
- dlouhé názvy tabulek si můžeme opět zkrátit pomocí příkazu as stejně tak, jako jsme krátili názvy sloupců
> select __column_name__ from __table_name__ *inner join* __another_table_name__ *on* __table_name.column_name__=__another_table_name.column_name__;
- naprosto stejné joinování tak, jak ho známe, akorát trochu upravená syntaxe
- vypíší se akorát ty řádky, které splňují podmínku za __on__
> select __column_name__ from __table_name__ *left join* __another_table_name__ *on* __table_name.column_name__=__another_table_name.column_name__;
- teď se vypíší všechny hodnoty z levého joinovacícho sloupce (__column_name__), i když nemají příslušného kandidáta na druhé tabulce
- příklad použití: jedna tabulka se zákazníky, druhá tabulka s produkty, které si zákazníci koupili - tabulku se zákazníky umístíme nalevo, tabulku s produkty napravo, mezi ně napíšeme left join syntaxi - příklad vypíše i ty zákazníky, kteří si nic nekoupili (kteří nejsou zavedení v tabulce koupených produktů)
>select __column_name__ from __table_name__ *right join* __another_table_name__ *on* __table_name.column_name__=__another_table_name.column_name__;
- teď se vypíší všechny hodnoty z pravého joinovacích sloupce (__another_column_name__), i když nemají příslušného kandidáta v levé tabulce (__column_name__)
- v příkladu použití se můžeme opět vrátit k tabulkami se zákazníky a koupenými produkty, opět dáme zákazníky nalevo a produkty napravo, ale tentokrát použijeme right join a ukážou se nám i produkty, které nikdo nekoupil
> select __column_name__ from __table_name__ *union* select __another_column_name__ from __another_table_name__;
- vypíše všechny sloupce z obou tabulek a smaže duplikáty
> select __column_name__ from __table_name__ *union all* select __another_column_name__ from __another_table_name__;
- vypíše všechny sloupce z obou tabulek a duplikáty nemaže
> *create view* __view_name__ *as* __select_statement__;
- vytvoří záznam, který obsahuje výstup ze __select_statementu__ a není pouze dočasný, můžeme si ho prohlížet, jako normální tabulku - dokonce se i automaticky aktualizuje
