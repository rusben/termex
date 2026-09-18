# BLOC 1: INICIACIÓ (20 exercicis)

### **Navegació i exploració bàsica**

**Exercici 1: Orientació inicial**
Obre una terminal nova i comprova tres coses: quin és el teu nom d'usuari, en quin directori et trobes actualment, i quina és la teva ruta absoluta (home directory).
- Comandes a utilitzar: `whoami`, `pwd`

**Exercici 2: Explorar el directori home**
Llista tot el contingut del teu directori personal, incloent els fitxers ocults (els que comencen amb punt). Identifica quins són fitxers i quins són directoris.
- Comandes a utilitzar: `ls -la`

**Exercici 3: Navegació pel sistema**
Navega cap al directori arrel del sistema (`/`) i després cap al directori `/tmp`. Observa com canvia el prompt. Torna al teu directori personal utilitzant una comanda ràpida.
- Comandes a utilitzar: `cd /`, `cd /tmp`, `cd ~` o `cd`

**Exercici 4: Explorar directoris del sistema**
Entra al directori `/var/log` i llista els 10 primers fitxers que hi trobis. Quin tipus d'informació creus que contenen aquests fitxers?
- Comandes a utilitzar: `cd /var/log`, `ls`

### **Creació i manipulació de fitxers**

**Exercici 5: Crear un espai de treball**
Al teu directori personal, crea una carpeta anomenada `practiques_terminal`. Dins d'aquesta carpeta, crea dues subcarpetes: `exercicis` i `notes`.
- Comandes a utilitzar: `mkdir`, `mkdir -p` (per crear múltiples nivells)

**Exercici 6: Crear fitxers buits**
Dins de `practiques_terminal/exercicis`, crea tres fitxers buits amb els noms: `exercici1.txt`, `exercici2.txt`, i `exercici3.txt`.
- Comandes a utilitzar: `touch`

**Exercici 7: Crear contingut amb echo**
Utilitza la comanda `echo` per escriure "Hola Terminal!" dins del fitxer `exercici1.txt`. Després verifica que el contingut s'ha guardat correctament.
- Comandes a utilitzar: `echo "Hola Terminal!" > exercici1.txt`, `cat exercici1.txt`

**Exercici 8: Afegir contingut a un fitxer**
Afegeix una segona línia al fitxer `exercici1.txt` amb el text "Segona línia". Atenció: no sobrescriure el contingut anterior!
- Comandes a utilitzar: `echo "Segona línia" >> exercici1.txt`, `cat exercici1.txt`

**Exercici 9: Copiar fitxers**
Fes una còpia de `exercici1.txt` i anomena-la `exercici1_backup.txt`. Després verifica que ambdós fitxers existeixen.
- Comandes a utilitzar: `cp`, `ls`

### **Visualització de contingut**

**Exercici 10: Llegir fitxers del sistema**
Visualitza el contingut del fitxer `/etc/hostname`. Què mostra?
- Comandes a utilitzar: `cat /etc/hostname`

**Exercici 11: Veure les primeres línies**
Visualitza només les 5 primeres línies del fitxer `/etc/passwd`.
- Comandes a utilitzar: `head -n 5 /etc/passwd`

**Exercici 12: Veure les últimes línies**
Visualitza les últimes 3 línies del fitxer `/var/log/syslog` (o `/var/log/auth.log` si no existeix).
- Comandes a utilitzar: `tail -n 3`

**Exercici 13: Navegar per fitxers llargs**
Utilitza la comanda `less` per explorar el fitxer `/etc/services`. Mou-te amunt i avall amb les fletxes, i surt amb la tecla `q`.
- Comandes a utilitzar: `less /etc/services`

### **Operacions bàsiques avançades**

**Exercici 14: Renombrar fitxers**
Canvia el nom del fitxer `exercici3.txt` a `exercici_final.txt`.
- Comandes a utilitzar: `mv`

**Exercici 15: Moure fitxers entre directoris**
Mou el fitxer `exercici1_backup.txt` de la carpeta `exercicis` a la carpeta `notes`.
- Comandes a utilitzar: `mv`

**Exercici 16: Eliminar fitxers**
Elimina el fitxer `exercici2.txt`. Confirma que ja no existeix.
- Comandes a utilitzar: `rm`, `ls`

**Exercici 17: Eliminar directoris buits**
Dins de `practiques_terminal`, crea una carpeta buida anomenada `temporal` i després elimina-la.
- Comandes a utilitzar: `mkdir`, `rmdir`

**Exercici 18: Eliminar directoris amb contingut**
Intenta eliminar la carpeta `notes` amb `rmdir`. Què passa? Ara elimina-la correctament juntament amb tot el seu contingut.
- Comandes a utilitzar: `rmdir`, `rm -r`

### **Informació del sistema**

**Exercici 19: Informació del sistema**
Mostra informació sobre el teu sistema: nom del nucli (kernel), versió del sistema operatiu, i arquitectura del processador.
- Comandes a utilitzar: `uname -r`, `lsb_release -a` o `cat /etc/os-release`, `uname -m`

**Exercici 20: Espai en disc**
Comprova quant espai en disc ocupa la teva carpeta `practiques_terminal` i quant espai lliure tens a la teva partició principal.
- Comandes a utilitzar: `du -sh practiques_terminal`, `df -h`

## Resum de noves comandes introduïdes:

- `whoami`: Mostra el nom d'usuari actual
- `echo`: Imprimeix text a la terminal o en un fitxer
- `cat`: Mostra el contingut complet d'un fitxer
- `head`: Mostra les primeres línies d'un fitxer
- `tail`: Mostra les últimes línies d'un fitxer
- `less`: Visualitzador paginat de fitxers
- `rmdir`: Elimina directoris buits
- `rm -r`: Elimina directoris amb contingut
- `uname`: Mostra informació del sistema
- `du`: Mostra l'ús de disc
- `df`: Mostra l'espai lliure al disc

## BLOC 2: NIVELL INTERMEDI (20 exercicis)

### **Permisos i seguretat de fitxers**

**Exercici 1: Analitzar permisos**
Llista el contingut de la carpeta `practiques_terminal/exercicis` amb el format detallat. Identifica què signifiquen les lletres i números que apareixen a l'esquerra de cada línia (propietari, grup, altres).
- Comandes a utilitzar: `ls -l`

**Exercici 2: Crear i executar un script**
Crea un fitxer anomenat `saluda.sh` i escriu-hi dins `echo "Hola, sóc un script!"`. Intenta executar-lo directament (`./saluda.sh`). Què passa? Ara dona-li permisos d'execució i torna-ho a provar.
- Comandes a utilitzar: `echo 'echo "Hola, sóc un script!"' > saluda.sh`, `chmod +x saluda.sh`, `./saluda.sh`

**Exercici 3: Permisos restrictius**
Canvia els permisos del fitxer `exercici1.txt` perquè **només** el propietari pugui llegir-lo i escriure-hi, i que la resta d'usuaris no tinguin cap permís. Verifica el canvi.
- Comandes a utilitzar: `chmod 600 exercici1.txt`, `ls -l exercici1.txt`

**Exercici 4: Permisos per a tothom (lectura)**
Modifica els permisos de `exercici1.txt` perquè el propietari pugui llegir i escriure, però que el grup i la resta d'usuaris només puguin llegir-lo.
- Comandes a utilitzar: `chmod 644 exercici1.txt`

### **Cerques avançades i filtratge de text**

**Exercici 5: Buscar fitxers per nom**
Utilitza la comanda `find` per buscar tots els fitxers que acabin en `.txt` dins de la carpeta `practiques_terminal` i els seus subdirectoris.
- Comandes a utilitzar: `find practiques_terminal -name "*.txt"`

**Exercici 6: Cercar text dins de fitxers**
Utilitza `grep` per buscar la paraula "Hola" dins del fitxer `exercici1.txt`.
- Comandes a utilitzar: `grep "Hola" exercici1.txt`

**Exercici 7: Cerca recursiva i insensible a majúscules**
Cerca la paraula "terminal" (en qualsevol combinació de majúscules/minúscules) dins de tots els fitxers de la carpeta `practiques_terminal`.
- Comandes a utilitzar: `grep -ri "terminal" practiques_terminal`

**Exercici 8: Buscar fitxers per mida**
Utilitza `find` per localitzar qualsevol fitxer dins del teu directori personal (`~`) que tingui una mida superior a 100 Kilobytes.
- Comandes a utilitzar: `find ~ -type f -size +100k`

### **Tuberías (Pipes) i Redirecció**

**Exercici 9: Comptar elements**
Utilitza la comanda `wc` (word count) per saber quantes línies, paraules i caràcters té el fitxer `/etc/passwd`.
- Comandes a utilitzar: `wc /etc/passwd`

**Exercici 10: Encadenar comandes (Pipe)**
Llista tots els processos que contenen la paraula "bash" combinant `ps` i `grep` mitjançant una tubería (`|`).
- Comandes a utilitzar: `ps aux | grep bash`

**Exercici 11: Ordenar i guardar**
Llista el contingut de `/etc`, ordena alfabèticament el resultat i guarda-lo en un fitxer anomenat `llista_etc.txt` dins de `practiques_terminal`.
- Comandes a utilitzar: `ls /etc | sort > practiques_terminal/llista_etc.txt`

**Exercici 12: Redirigir errors**
Intenta llistar el contingut d'un directori on no tens permisos (ex: `/root`). Redirigeix només el missatge d'error a un fitxer anomenat `errors.log` a la teva carpeta, de manera que no es mostri per pantalla.
- Comandes a utilitzar: `ls /root 2> practiques_terminal/errors.log`

### **Gestió de processos**

**Exercici 13: Observar processos en temps real**
Obre la comanda `top` per veure els processos que consumeixen més recursos. Prem la tecla `q` per sortir-ne.
- Comandes a utilitzar: `top`

**Exercici 14: Executar en segon pla**
Executa la comanda `sleep 100` perquè s'executi en segon pla (background) afegint un `&` al final. Després, comprova que està executant-se.
- Comandes a utilitzar: `sleep 100 &`, `jobs`

**Exercici 15: Trobar el PID d'un procés**
Utilitza `ps` i `grep` per trobar el número d'identificació de procés (PID) del `sleep` que acabes de llançar.
- Comandes a utilitzar: `ps aux | grep sleep`

**Exercici 16: Aturar un procés**
Utilitza la comanda `kill` seguida del PID que has trobat a l'exercici anterior per aturar el procés `sleep`. Verifica amb `jobs` o `ps` que ja no existeix.
- Comandes a utilitzar: `kill <PID>`, `jobs`

### **Compressió, arxiu i entorn**

**Exercici 17: Comprimir una carpeta**
Crea un arxiu comprimit en format `.tar.gz` que contingui tota la carpeta `practiques_terminal/exercicis`. Anomena l'arxiu `backup_exercicis.tar.gz`.
- Comandes a utilitzar: `tar -czvf backup_exercicis.tar.gz practiques_terminal/exercicis`

**Exercici 18: Descomprimir en un lloc diferent**
Crea una carpeta nova anomenada `restauracio` i descomprimeix l'arxiu `backup_exercicis.tar.gz` dins d'aquesta carpeta.
- Comandes a utilitzar: `mkdir restauracio`, `tar -xzvf backup_exercicis.tar.gz -C restauracio`

**Exercici 19: Crear un àlies**
Crea un àlies temporal anomenat `ll` que sigui equivalent a executar `ls -la`. Prova l'àlies i després elimina'l.
- Comandes a utilitzar: `alias ll='ls -la'`, `ll`, `unalias ll`

**Exercici 20: Consultar variables d'entorn**
Utilitza `echo` per mostrar el valor de les variables d'entorn `$USER`, `$HOME` i `$PATH`. Explica breument què fa cadascuna.
- Comandes a utilitzar: `echo $USER`, `echo $HOME`, `echo $PATH`

## Resum de noves comandes i conceptes introduïts:

- `chmod`: Canvia els permisos d'accés als fitxers (ex: `+x`, `644`, `600`).
- `find`: Eina potent per cercar fitxers i directoris per nom, mida o tipus.
- `grep`: Filtra línies de text que coincideixen amb un patró (`-i` per ignorar majúscules, `-r` per recursiu).
- `|` (Pipe): Passa la sortida d'una comanda com a entrada de la següent.
- `>` i `>>`: Redirecció de sortida (sobreescriure o afegir).
- `2>`: Redirecció específica del flux d'errors (stderr).
- `wc`: Compta línies, paraules i bytes.
- `sort`: Ordena línies de text alfabèticament o numèricament.
- `ps` / `top`: Mostren informació sobre els processos en execució.
- `kill`: Envia un senyal (per defecte, de terminació) a un procés pel seu PID.
- `tar`: Eina d'arxivat i compressió (`-c` crear, `-x` extreure, `-z` gzip, `-v` verbós, `-f` fitxer).
- `alias` / `unalias`: Crea o elimina dreceres de comandes personalitzades.

## BLOC 3: NIVELL AVANÇAT (20 exercicis)

### **Scripts Bash: Automatització bàsica**

**Exercici 1: El teu primer script amb variables**
Crea un script anomenat `info_sistema.sh` que mostri per pantalla el nom d'usuari, la data actual i el directori on s'està executant. Utilitza les variables `$USER`, `$(date)` i `$(pwd)`.
- Comandes a utilitzar: `nano info_sistema.sh`, `chmod +x info_sistema.sh`, `./info_sistema.sh`
- Contingut suggerit:
  ```bash
  #!/bin/bash
  echo "Usuari: $USER"
  echo "Data: $(date)"
  echo "Directori: $(pwd)"
  ```

**Exercici 2: Script amb arguments**
Crea un script anomenat `saluda.sh` que rebi un nom com a argument i mostri "Hola, [nom]!". Si no es passa cap argument, ha de mostrar un missatge d'error.
- Comandes a utilitzar: `nano saluda.sh`, `./saluda.sh Maria`
- Pista: Utilitza `$1` per al primer argument i `$#` per comptar arguments.

**Exercici 3: Condicional if en un script**
Crea un script anomenat `comprova.sh` que rebi un nom de fitxer com a argument i digui si existeix o no.
- Comandes a utilitzar: `nano comprova.sh`
- Pista: Utilitza `if [ -f "$1" ]; then ... else ... fi`

**Exercici 4: Bucle for per processar fitxers**
Crea un script anomenat `compta_linies.sh` que recorri tots els fitxers `.txt` de la carpeta actual i mostri el número de línies de cadascun.
- Comandes a utilitzar: `nano compta_linies.sh`
- Pista: `for fitxer in *.txt; do wc -l "$fitxer"; done`

### **Gestió de paquets i serveis del sistema**

**Exercici 5: Actualitzar el sistema**
Actualitza la llista de paquets disponibles i després actualitza tots els paquets instal·lats del sistema.
- Comandes a utilitzar: `sudo apt update`, `sudo apt upgrade -y`

**Exercici 6: Instal·lar i desinstal·lar programari**
Instal·la el paquet `htop` (un visor de processos millorat) i després comprova la seva versió. Finalment, desinstal·la'l.
- Comandes a utilitzar: `sudo apt install htop`, `htop --version`, `sudo apt remove htop`

**Exercici 7: Cercar paquets**
Utilitza `apt search` per trobar paquets relacionats amb "editor de text". Instal·la el que et sembli més interessant (per exemple, `nano` o `vim`).
- Comandes a utilitzar: `apt search "editor de text"`, `sudo apt install vim`

**Exercici 8: Gestionar serveis amb systemd**
Comprova l'estat del servei SSH (`ssh` o `sshd`). Si no està actiu, inicia'l. Després, mira els últims 20 registres del servei.
- Comandes a utilitzar: `systemctl status ssh`, `sudo systemctl start ssh`, `sudo journalctl -u ssh -n 20`

### **Xarxa i connectivitat**

**Exercici 9: Comprovar connectivitat**
Utilitza `ping` per comprovar si tens connexió amb el servidor DNS de Google (`8.8.8.8`). Atura el ping amb `Ctrl+C` després de 5 paquets.
- Comandes a utilitzar: `ping -c 5 8.8.8.8`

**Exercici 10: Resolució de noms DNS**
Utilitza `dig` o `nslookup` per obtenir la informació DNS del domini `ubuntu.com`. Quina adreça IP té associada?
- Comandes a utilitzar: `dig ubuntu.com` o `nslookup ubuntu.com`

**Exercici 11: Descarregar fitxers d'Internet**
Utilitza `wget` per descarregar la pàgina principal d'`example.com` i desa-la com `exemple.html`. Després visualitza el seu contingut amb `less`.
- Comandes a utilitzar: `wget -O exemple.html https://example.com`, `less exemple.html`

**Exercici 12: Consultar ports oberts**
Utilitza `ss` (successor de `netstat`) per llisten tots els ports TCP que estan escoltant al teu sistema.
- Comandes a utilitzar: `ss -tln` o `sudo ss -tlnp`

### **Gestió d'usuaris i permisos avançats**

**Exercici 13: Crear un usuari nou**
Crea un usuari anomenat `alumne1` amb directori personal i assigna-li una contrasenya. Després, comprova que s'ha creat correctament al fitxer `/etc/passwd`.
- Comandes a utilitzar: `sudo useradd -m alumne1`, `sudo passwd alumne1`, `grep alumne1 /etc/passwd`

**Exercici 14: Gestionar grups**
Crea un grup anomenat `classe` i afegeix l'usuari `alumne1` a aquest grup. Verifica els grups als quals pertany.
- Comandes a utilitzar: `sudo groupadd classe`, `sudo usermod -aG classe alumne1`, `groups alumne1`

**Exercici 15: Canviar d'usuari**
Utilitza `su` per canviar a l'usuari `alumne1`, executa `whoami` per confirmar-ho, i després torna al teu usuari original.
- Comandes a utilitzar: `su - alumne1`, `whoami`, `exit`

**Exercici 16: Permisos avançats amb chown**
Crea un fitxer anomenat `compartit.txt` i fes que el propietari sigui `alumne1` i el grup `classe`. Dona permisos de lectura i escriptura al propietari i al grup, però només lectura a la resta.
- Comandes a utilitzar: `touch compartit.txt`, `sudo chown alumne1:classe compartit.txt`, `chmod 664 compartit.txt`, `ls -l compartit.txt`

### **Automatització amb Cron**

**Exercici 17: Programar una tasca simple**
Edita el teu crontab (`crontab -e`) i programa una tasca que executi `echo "Hola Cron"` cada dia a les 14:00h, guardant la sortida a `cron_log.txt`.
- Comandes a utilitzar: `crontab -e`
- Línia a afegir: `0 14 * * * echo "Hola Cron" >> ~/cron_log.txt`

**Exercici 18: Llistar i eliminar tasques programades**
Llista totes les teves tasques programades amb `crontab` i després elimina-les totes amb l'opció corresponent.
- Comandes a utilitzar: `crontab -l`, `crontab -r`

### **Processament avançat de text**

**Exercici 19: Processar text amb awk**
Utilitza `awk` per mostrar només el nom d'usuari (primera columna) i el seu shell (última columna) del fitxer `/etc/passwd`, separats per un espai.
- Comandes a utilitzar: `awk -F: '{print $1, $7}' /etc/passwd`

**Exercici 20: Substituir text amb sed**
Crea un fitxer anomenat `prova.txt` amb el text "Hola món, adéu món". Utilitza `sed` per substituir la primera aparició de "món" per "terminal" i desa el resultat a `prova_modificada.txt`.
- Comandes a utilitzar: 
  ```bash
  echo "Hola món, adéu món" > prova.txt
  sed 's/món/terminal/' prova.txt > prova_modificada.txt
  cat prova_modificada.txt
  ```

## Resum de conceptes i comandes avançades introduïdes:

### **Automatització i Scripts**
- `#!/bin/bash`: Shebang per indicar l'intèrpret
- `$1`, `$2`, `$#`: Arguments passats a un script
- `if [ -f "$fitxer" ]`: Condicionals
- `for ... in ... do ... done`: Bucle per iterar
- `$(comanda)`: Substitució de comandes

### **Gestió del sistema**
- `apt update / upgrade / install / remove / search`: Gestió de paquets
- `systemctl status / start / stop / restart`: Control de serveis
- `journalctl`: Visualització de registres del sistema

### **Xarxa**
- `ping`: Comprova connectivitat
- `dig / nslookup`: Resolució DNS
- `wget / curl`: Descàrrega de fitxers des d'Internet
- `ss`: Mostra connexions i ports oberts

### **Administració d'usuaris**
- `useradd / usermod / passwd`: Creació i modificació d'usuaris
- `groupadd`: Creació de grups
- `chown`: Canvia propietari i grup d'un fitxer
- `su`: Canvia d'usuari

### **Automatització temporal**
- `crontab -e / -l / -r`: Editar, llistar i eliminar tasques programades
- Sintaxi Cron: `minut hora dia_mes mes dia_setmana comanda`

### **Processament avançat de text**
- `awk`: Processament de columnes i camps
- `sed`: Substitució i edició de fluxos de text
- `-F`: Delimitador de camps a awk

## Exercici final integrador (opcional)

> **Projecte: Script de backup automatitzat**
> Crea un script anomenat `backup.sh` que:
> 1. Rebi com a argument una carpeta a copiar
> 2. Comprovi si la carpeta existeix (condicional)
> 3. Creï un arxiu `.tar.gz` amb la data actual al nom
> 4. Mogui l'arxiu a una carpeta `~/backups`
> 5. Registri l'operació a un fitxer `backup.log` amb data i hora
> 6. Programa'l amb `cron` per executar-se cada diumenge a les 23:00h
