# DOCKER IMAGE
- tento příkaz nám umožňuje spravovat stažené obrazy
- pokud spustíme pouze příkaz *docker image* bez dalších argumentů, vyběhne nám nápověda:
	- ![[Pasted image 20230506081330.png]]
## DOCKER IMAGE BUILD
## DOCKER IMAGE LS
- tento příkaz zobrazí všechny stáhnuté obrazy
- ukázka výstupu:
	- ![[Pasted image 20230506081604.png]]
- pokud přidáme switch -q, ukážou se nám pouze ID obrazů:
	- ![[Pasted image 20230506081725.png]]
## DOCKER IMAGE PULL
- stejné jako docker pull (viz DOCKER PULL)
## DOCKER IMAGE RM
- odstraní obraz z místního úložiště

# DOCKER PULL
- obrazy docker containerů lze stáhnout pomocí tohoto příkazu (docker pull *image_name*)
- zde jsem například stáhnul webový server nginx:
	- ![[Pasted image 20230506080655.png]]
- tímto příkazem jsme stáhli poslední (latest) verzi nginx obrazu, kdybychom chtěli stáhnout dřívější verzi, musíme použít jiný tag
- podle výstupu příkazu (2 řádek) vidíme, že pokud žádný tag nespecifikujeme, bude použit ten výchozí (latest)
- tag specifikujeme tak, že za název obrazu napíšeme *:tag*, například pro Ubuntu verzi 18.04 napíšeme: *docker pull ubuntu:18.04*

# DOCKER RUN
- za pomoci specifikovaného obrazu tento příkaz vytvoří běžící container