Termíny
- SERP - Search Engine Result Page - výsledky vyhedávání po zadání dotazu
Jak google fungoval?
- Celé to bylo založeno na principu **page rank**. každá stránka dostala skóre, které reprezentovalo její důvěryhodnost a "šlechetnost", pokud na nějakou stránku odkazovalo více šlechetných stránek, stala se z nové stránky také šlechetná stránka.
- Tento princip byl poprvé uplatněn v search enginu **Backrub**
Jak funguje google dnes?
- Kromě principu page rank používá i další sofistikovanější metody, například používá boty, kterým se také říká pavouci (spiders), kteří objevují nové stránky, které byly zrovna vytvořeny (říká se tomu web crawling)
- každá stránka má k sobě přiřazeny tzv. webové signály, které o stránce říkají, jak je spolehlivá, do této metriky se započítává page rank, vitalita stránky, doba načítání stránky a další parametry.
- RankBrain je AI, která se zaměřuje na sémantiku vyhledávaného dotazu a přiřazuje ji ke kontextu webových stránek
- google také sdružuje webové stránky s podobnými znaky (clustering - shromažďuje je do clusterů) = klasifikace
- google automaticky přehlíží hláskovací a gramatické chyby dotazů, zvládne i k jednotlivým slovům přiřazovat synonyma
- fungování google search enginu je velká záhada někdy i pro samotné google vývojáře, protože je velmi složitý a výstupy umělých inteligencí je také těžké předpovídat
- relevance webové stránky vzhledem k dotazu je tedy závislá na mnoha faktorech
- pokud by nějaký kyberbezpečnostní člověk napsal do vyhledávacího pole dotaz grep, pravděpodobně by mu google podal výsledky o linuxovém příkazu, nikoliv o citrusu, google totiž k vyhledávacím faktorům přidává vaši lokaci, jazyk, často navštěvované stránky, historii vyhledávání a další věci, které mu pomohou určit, jaký grep myslíte
Jak formovat dotazy pro google?
- Chce to přesné, krátké a stručné požadavky, bez zbytečných nebo opakujících se slov.
- Fragmentuj svou otázku na několik podotázek.
- Nevyhledávat: Ahoj milý google, pomohl by jsi mi prosím tě s úkolem do češtiny a řekl bys mi, co je to shoda podmětu s přísudkem?
- Vyhledávat: Shoda podmětu s přísudkem gramatika.
- googlu nezáleží na gramatice, hláskování a velikosti písmen
- googlu ale záleží na pořádku slov (eternal blue místo blue eternal)
Podtržítko
- podtržítko použíté v dotazu indikuje googlu, že má doplnit slovo, které zadavatel pravděpodobné nezná
- příklad: dotaz: exploit _ blue
	- google automaticky vyhledá eternal blue
Cool easteregg
- pokud do vyhledávacího pole napíšete frází _do a barrell roll_ nebo _z or r twice_, tak se webová stránka vyhledaného výrazu otočí
Lateral browsing
- otevírání několika odkazů na nové stránce ve výsledcích vyhledávání, které usnadní a zrychlí vyhledávání
TLDčka
- při vyhledávání je také radno se dívat na konce URL adres, tzv. TLD domény, které naznačují typ obsahu na stránce (.edu - vzdělávací obsah, .gov - vládní stránky, .cz - české stránky, .io - stránky, které měly odkazovat na obsah z anglického BRIOTu, ale počítačoví mágové je převzali jako input/output stránky, které znějí cool, .dev - vývojářské stránky)
Kritika výsledků
- je potřeba vyhledávat obecné, nikoliv konkrétní otázky (ne _Je na světě 25 milionů programátorů_, ale _Kolik je na světě programátorů_ ano)
- vyhledej si několik odpovědí z několika důvěryhodných zdrojů a několika jiných názorových skupin
Vyhledávací operátory

Matching Operators
- "" - výsledky musí obsahovat přesný výraz uvedený v závorce, hodí se to na zdůraznění výrazu v uvozovkách (chceme dát najevo, že to není spellovací nebo gramatická chyba)
	- dotaz: zelené papriky, výsledek: pár zelených paprik, jedna červená paprika, dvě žluté, potom zase pár zelených
	- dotaz: "zelené papriky", výsledek: jenom zelené papriky
- - (mínus) - výsledky nebudou obsahovat výraz uvedený za mínus symbolem
	- dotaz: zelené papriky, výsledek: normální zelené papriky
	- dotaz: zelené papriky -šťopky, výsledek: zelené papriky bez šťopek (nadsázka)
- * - žolík, wildcard, zástupce - google si za symbol hvězdičky dosadí všemožná slova přihlížejíc ke kontextu
	- dotaz: Linus * Linux, výsledek: Linux Torvalds Linux
- around(x) - zobrazí výsledky, které mají x slov okolo slova před operátorem slovo po operátoru
	- dotaz: office around(3) login, výsledek: Microsoft Office Portal User Login page (nebo něco podobnýho)