> docker help
- zobrazí nápovědu k celému programu docker, výstup příkazu je rozdělen do tří kategorií:
	- Možnosti (Options) - obsahuje switche
	- Příkazy pro správu (Management Commands) - obsahuje podpříkazy určené pro správu aplikace
	- Příkazy (Commands) - obsahuje ostatní podpříkazy
- podpříkazy jsou zvlášním typem switche, který nevyžaduje - nebo -- (příklad: docker **help**, gobuster **dir**,)
> docker volume ls
- zobrazí všechny volumes (uložené docker containery)
> docker container ls/docker ps
- zobrazí běžící containery (po přidání switche -a zobrazí i ty nespuštěné)
> docker image ls
- zobrazí všechny obrazy disků (images)
> docker ps -a/docker container ls -a
- zobrazí i zastavené kontejnery
> docker container rename *old_name* *new_name*
- přejmenuje container

