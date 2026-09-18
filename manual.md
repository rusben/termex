# MANUAL DE COMANDES DEL TERMINAL UBUNTU

## ÍNDEX

1. [Navegació i exploració](#1-navegació-i-exploració)
2. [Gestió de fitxers i directoris](#2-gestió-de-fitxers-i-directoris)
3. [Visualització de contingut](#3-visualització-de-contingut)
4. [Permisos i propietat](#4-permisos-i-propietat)
5. [Cerca i filtratge](#5-cerca-i-filtratge)
6. [Tuberíes i redirecció](#6-tuberíes-i-redirecció)
7. [Gestió de processos](#7-gestió-de-processos)
8. [Compressió i arxivat](#8-compressió-i-arxivat)
9. [Informació del sistema](#9-informació-del-sistema)
10. [Gestió de paquets](#10-gestió-de-paquets)
11. [Xarxa i connectivitat](#11-xarxa-i-connectivitat)
12. [Gestió d'usuaris i grups](#12-gestió-dusuaris-i-grups)
13. [Automatització i scripts](#13-automatització-i-scripts)
14. [Processament avançat de text](#14-processament-avançat-de-text)
15. [Variables d'entorn i àlies](#15-variables-dentorn-i-àlies)
16. [Comandes del tutorial Termicat](#16-comandes-del-tutorial-termicat)

## 1. NAVEGACIÓ I EXPLORACIÓ

### `pwd` (Print Working Directory)
Mostra la ruta absoluta del directori actual.
```bash
pwd
# Sortida: /home/usuari/practiques_terminal
```

### `ls` (List)
Llista el contingut d'un directori.
```bash
ls                    # Llista bàsica
ls -l                 # Format detallat (permisos, propietari, mida, data)
ls -a                 # Inclou fitxers ocults (comencen amb .)
ls -la                # Combinat: detallat + ocults
ls -lh                # Mides en format llegible (K, M, G)
ls -lS                # Ordenat per mida (més grans primer)
ls -lt                # Ordenat per data de modificació
```

### `cd` (Change Directory)
Canvia el directori de treball actual.
```bash
cd /ruta/absoluta     # Navega a una ruta absoluta
cd carpeta            # Navega a una subcarpeta (ruta relativa)
cd ..                 # Puja al directori pare
cd ../..              # Puja dos nivells
cd ~                  # Torna al directori personal (home)
cd -                  # Torna al directori anterior
cd                    # Sense arguments = torna a ~
```

## 2. GESTIÓ DE FITXERS I DIRECTORIS

### `mkdir` (Make Directory)
Crea directoris nous.
```bash
mkdir carpeta                    # Crea una carpeta
mkdir carpeta1 carpeta2          # Crea diverses carpetes
mkdir -p pare/fill/net           # Crea estructura completa de carpetes
```

### `touch`
Crea fitxers buits o actualitza la data de modificació d'un fitxer existent.
```bash
touch fitxer.txt                 # Crea un fitxer buit
touch f1.txt f2.txt f3.txt       # Crea diversos fitxers
```

### `cp` (Copy)
Copia fitxers o directoris.
```bash
cp origen.txt desti.txt                    # Copia un fitxer
cp fitxer.txt ../                          # Copia al directori pare
cp -r carpeta_origen carpeta_desti         # Copia un directori (recursiu)
cp -i origen.txt desti.txt                 # Demana confirmació si sobrescriu
```

### `mv` (Move)
Mou o renomena fitxers i directoris.
```bash
mv antic.txt nou.txt                       # Renomena un fitxer
mv fitxer.txt /altra/carpeta/              # Mou a un altre lloc
mv -i origen.txt desti.txt                 # Demana confirmació
```

### `rm` (Remove)
Elimina fitxers o directoris.
```bash
rm fitxer.txt                              # Elimina un fitxer
rm -i fitxer.txt                           # Demana confirmació
rm -r carpeta                              # Elimina directori i contingut (recursiu)
rm -rf carpeta                             # Força l'eliminació sense preguntes (PERILL!)
```

### `rmdir`
Elimina directoris **buits**.
```bash
rmdir carpeta_buida                        # Només funciona si està buida
```

## 3. VISUALITZACIÓ DE CONTINGUT

### `cat` (Concatenate)
Mostra el contingut complet d'un fitxer.
```bash
cat fitxer.txt                             # Mostra tot el contingut
cat -n fitxer.txt                          # Amb números de línia
cat f1.txt f2.txt                          # Concatena diversos fitxers
```

### `echo`
Imprimeix text a la terminal o escriu en fitxers.
```bash
echo "Hola món"                            # Mostra text per pantalla
echo "text" > fitxer.txt                   # Escriu (sobreescriu) en un fitxer
echo "més text" >> fitxer.txt              # Afegeix al final del fitxer
echo $USER                                 # Mostra el valor d'una variable
```

### `head`
Mostra les primeres línies d'un fitxer (per defecte, 10).
```bash
head fitxer.txt                            # Primeres 10 línies
head -n 5 fitxer.txt                       # Primeres 5 línies
```

### `tail`
Mostra les últimes línies d'un fitxer (per defecte, 10).
```bash
tail fitxer.txt                            # Últimes 10 línies
tail -n 3 fitxer.txt                       # Últimes 3 línies
tail -f /var/log/syslog                    # Segueix el fitxer en temps real
```

### `less`
Visualitzador paginat de fitxers (permet navegar).
```bash
less fitxer.txt
# Dins de less:
#   Fletxes / PgUp / PgDn → Navegar
#   /text                 → Cercar
#   n                     → Següent coincidència
#   q                     → Sortir
```

### `nano`
Editor de text senzill per a terminal.
```bash
nano fitxer.txt                            # Obre o crea un fitxer
# Dins de nano:
#   Ctrl+O    → Desar
#   Ctrl+X    → Sortir
#   Ctrl+K    → Tallar línia
#   Ctrl+U    → Enganxar
```

## 4. PERMISOS I PROPIETAT

### `chmod` (Change Mode)
Canvia els permisos d'accés a fitxers i directoris.

**Sistema numèric (recomanat):**
- `4` = lectura (r)
- `2` = escriptura (w)
- `1` = execució (x)

```bash
chmod 755 fitxer       # rwxr-xr-x (propietari tot, resta llegir+executar)
chmod 644 fitxer       # rw-r--r-- (propietari llegir+escriure, resta llegir)
chmod 600 fitxer       # rw------- (només propietari)
chmod +x script.sh     # Afegeix permís d'execució
chmod -w fitxer        # Treu permís d'escriptura
```

**Sistema simbòlic:**
- `u` = usuari (propietari), `g` = grup, `o` = altres, `a` = tots
- `+` afegir, `-` treure, `=` assignar

```bash
chmod u+x script.sh        # Afegeix execució al propietari
chmod g-w fitxer           # Treu escriptura al grup
chmod a+r fitxer           # Afegeix lectura a tothom
chmod u=rwx,g=rx,o= fitxer # Assigna permisos exactes
```

### `chown` (Change Owner)
Canvia el propietari i/o grup d'un fitxer.
```bash
sudo chown usuari fitxer              # Canvia propietari
sudo chown usuari:grup fitxer         # Canvia propietari i grup
sudo chown -R usuari:grup carpeta/    # Recursiu (tota la carpeta)
```

## 5. CERCA I FILTRATGE

### `find`
Cerca fitxers i directoris per diversos criteris.
```bash
find . -name "*.txt"                   # Cerca per nom (actual i subdirectoris)
find /home -name "document*"           # Cerca per patró
find . -type f -size +100k             # Fitxers més grans de 100KB
find . -type d -name "backup*"         # Només directoris
find . -mtime -7                       # Modificats en els últims 7 dies
find . -empty                          # Fitxers o directoris buits
```

### `grep`
Cerca patrons de text dins de fitxers o fluxos.
```bash
grep "patró" fitxer.txt                # Cerca una paraula
grep -i "patró" fitxer.txt             # Ignora majúscules/minúscules
grep -r "patró" carpeta/               # Recursiu (tota la carpeta)
grep -ri "patró" carpeta/              # Recursiu + insensible a majúscules
grep -n "patró" fitxer.txt             # Mostra número de línia
grep -v "patró" fitxer.txt             # Línies que NO contenen el patró
grep -c "patró" fitxer.txt             # Compta coincidències
```

### `which`
Mostra la ruta d'un executable.
```bash
which python3                          # /usr/bin/python3
which ls                               # /usr/bin/ls
```

## 6. TUBERÍES I REDIRECCIÓ

### Operadors de redirecció

| Operador | Descripció | Exemple |
|----------|------------|---------|
| `>` | Redirigeix sortida (sobreescriu) | `ls > llista.txt` |
| `>>` | Redirigeix sortida (afegeix) | `echo "text" >> fitxer.txt` |
| `<` | Redirigeix entrada | `sort < fitxer.txt` |
| `2>` | Redirigeix errors | `ls /root 2> errors.log` |
| `&>` | Redirigeix sortida + errors | `comanda &> tot.log` |
| `\|` | Tubería (pipe) | `ls \| grep ".txt"` |

### Exemples pràctics
```bash
ls /etc | sort > llista_etc.txt        # Llista ordenada a un fitxer
ps aux | grep bash                     # Filtra processos que contenen "bash"
cat fitxer.txt | wc -l                 # Compta línies
find . -name "*.log" | xargs rm        # Elimina tots els .log trobats
```

### `sort`
Ordena línies de text.
```bash
sort fitxer.txt                        # Ordre alfabètic
sort -r fitxer.txt                     # Ordre invers
sort -n numeros.txt                    # Ordre numèric
sort -u fitxer.txt                     # Elimina duplicats
```

### `wc` (Word Count)
Compta línies, paraules i bytes.
```bash
wc fitxer.txt                          # Línies, paraules, bytes
wc -l fitxer.txt                       # Només línies
wc -w fitxer.txt                       # Només paraules
wc -c fitxer.txt                       # Només bytes/caràcters
```

## 7. GESTIÓ DE PROCESSOS

### `ps` (Process Status)
Mostra informació sobre processos en execució.
```bash
ps                                     # Processos de la sessió actual
ps aux                                 # Tots els processos del sistema
ps aux | grep firefox                  # Filtra processos
ps -ef                                 # Format complet
```

### `top` / `htop`
Monitor de processos en temps real.
```bash
top                                    # Monitor bàsic
htop                                   # Versió millorada (cal instal·lar)
# Dins de top/htop:
#   q        → Sortir
#   k        → Matar un procés
#   Fletxes  → Navegar
```

### `jobs`
Mostra tasques en segon pla de la sessió actual.
```bash
sleep 100 &                            # Executa en segon pla
jobs                                   # Llista tasques en background
```

### `kill`
Envia senyals a processos (per defecte, els termina).
```bash
kill PID                               # Termina un procés pel seu PID
kill -9 PID                            # Força la terminació (SIGKILL)
killall nom_procés                     # Termina tots els processos amb aquest nom
```

### `&` i `Ctrl+Z`
```bash
comanda &                              # Executa en segon pla
# Ctrl+Z                              → Pausa el procés en primer pla
bg                                     # Reprèn un procés pausat en segon pla
fg                                     # Porta un procés de segon pla a primer pla
```

## 8. COMPRESSIÓ I ARXIVAT

### `tar` (Tape Archive)
Eina d'arxivat i compressió.
```bash
# Crear arxius
tar -cvf arxiu.tar carpeta/            # Crea arxiu .tar (sense comprimir)
tar -czvf arxiu.tar.gz carpeta/        # Crea arxiu .tar.gz (comprimit amb gzip)
tar -cjvf arxiu.tar.bz2 carpeta/       # Crea arxiu .tar.bz2 (comprimit amb bzip2)

# Extreure arxius
tar -xvf arxiu.tar                     # Extreu un .tar
tar -xzvf arxiu.tar.gz                 # Extreu un .tar.gz
tar -xzvf arxiu.tar.gz -C /desti/      # Extreu a un directori específic

# Opcions comunes:
# -c = create, -x = extract
# -z = gzip, -j = bzip2
# -v = verbose (mostra el que fa)
# -f = file (especifica el nom de l'arxiu)
```

### `zip` / `unzip`
```bash
zip -r arxiu.zip carpeta/              # Comprimeix recursivament
unzip arxiu.zip                        # Descomprimeix
unzip arxiu.zip -d /desti/             # Descomprimeix a un directori
```

## 9. INFORMACIÓ DEL SISTEMA

### `uname`
Mostra informació del nucli i sistema.
```bash
uname                                  # Nom del sistema (Linux)
uname -r                               # Versió del nucli
uname -m                               # Arquitectura (x86_64, aarch64...)
uname -a                               # Tota la informació
```

### `lsb_release` / `cat /etc/os-release`
Informació de la distribució.
```bash
lsb_release -a                         # Informació d'Ubuntu
cat /etc/os-release                    # Detalls de la distribució
```

### `whoami`
Mostra el nom de l'usuari actual.
```bash
whoami                                 # usuari
```

### `df` (Disk Free)
Mostra l'espai lliure al disc.
```bash
df -h                                  # Format llegible (K, M, G)
df -h /                                # Només la partició arrel
```

### `du` (Disk Usage)
Mostra l'espai ocupat per fitxers i directoris.
```bash
du -sh carpeta/                        # Mida total de la carpeta
du -sh *                               # Mida de cada element al directori actual
du -h --max-depth=1                    # Un nivell de profunditat
```

### `free`
Mostra l'ús de memòria RAM.
```bash
free -h                                # Format llegible
```

### `date`
Mostra la data i hora actual.
```bash
date                                   # Data i hora actual
date +"%Y-%m-%d"                       # Format personalitzat
```

### `hostname`
Mostra el nom de l'equip.
```bash
hostname                               # Nom de l'equip
cat /etc/hostname                      # Fitxer de configuració
```

## 10. GESTIÓ DE PAQUETS

### `apt` (Advanced Package Tool)
Gestor de paquets d'Ubuntu/Debian.
```bash
sudo apt update                        # Actualitza la llista de paquets
sudo apt upgrade                       # Actualitza paquets instal·lats
sudo apt upgrade -y                    # Actualitza sense demanar confirmació
sudo apt install paquet                # Instal·la un paquet
sudo apt remove paquet                 # Desinstal·la un paquet
sudo apt purge paquet                  # Desinstal·la + fitxers de configuració
sudo apt autoremove                    # Elimina dependències no necessàries
apt search "text"                      # Cerca paquets
apt show paquet                        # Informació d'un paquet
apt list --installed                   # Llista paquets instal·lats
```

## 11. XARXA I CONNECTIVAT

### `ping`
Comprova connectivitat amb un host.
```bash
ping google.com                        # Ping continu (Ctrl+C per aturar)
ping -c 5 8.8.8.8                      # 5 paquets i para
```

### `dig` / `nslookup`
Consulta informació DNS.
```bash
dig ubuntu.com                         # Informació DNS completa
dig ubuntu.com +short                  # Només la IP
nslookup ubuntu.com                    # Alternativa més simple
```

### `wget`
Descarrega fitxers d'Internet.
```bash
wget https://exemple.com/fitxer.zip              # Descarrega
wget -O nom_nou.zip https://exemple.com/fitxer.zip  # Desa amb un altre nom
wget -c https://exemple.com/fitxer.zip           # Reprèn descàrrega interrompuda
```

### `curl`
Transfereix dades des de o cap a un servidor.
```bash
curl https://exemple.com                         # Mostra el contingut
curl -O https://exemple.com/fitxer.zip           # Descarrega
curl -I https://exemple.com                      # Només capçaleres HTTP
```

### `ss` (Socket Statistics)
Mostra connexions de xarxa i ports.
```bash
ss -tln                            # Ports TCP escoltant
ss -tlnp                           # Amb informació del procés
ss -a                              # Totes les connexions
```

## 12. GESTIÓ D'USUARIS I GRUPS

### `useradd` / `usermod` / `passwd`
Gestió d'usuaris.
```bash
sudo useradd -m nou_usuari                 # Crea usuari amb directori personal
sudo passwd nou_usuari                     # Assigna contrasenya
sudo usermod -aG grup usuari               # Afegeix usuari a un grup
sudo userdel -r usuari                     # Elimina usuari i el seu directori
```

### `groupadd`
Crea grups d'usuaris.
```bash
sudo groupadd nom_grup                     # Crea un grup
sudo groupdel nom_grup                     # Elimina un grup
```

### `su` (Switch User)
Canvia d'usuari.
```bash
su - usuari                                # Canvia a un altre usuari
sudo su -                                  # Canvia a root
exit                                       # Torna a l'usuari anterior
```

### `groups` / `id`
Mostra informació de grups.
```bash
groups                                     # Grups de l'usuari actual
groups usuari                              # Grups d'un usuari específic
id usuari                                  # UID, GID i grups
```


## 13. AUTOMATITZACIÓ I SCRIPTS

### Scripts Bash
```bash
#!/bin/bash
# Això és un comentari

# Variables
NOM="Maria"
echo "Hola, $NOM"

# Arguments
echo "Primer argument: $1"
echo "Segon argument: $2"
echo "Nombre d'arguments: $#"
echo "Nom de l'script: $0"

# Substitució de comandes
DATA=$(date)
echo "Avui és $DATA"

# Condicionals
if [ -f "$1" ]; then
    echo "El fitxer existeix"
else
    echo "El fitxer no existeix"
fi

# Bucles
for fitxer in *.txt; do
    echo "Processant: $fitxer"
done
```

### `crontab`
Programa tasques automàtiques.
```bash
crontab -e                               # Edita les tasques programades
crontab -l                               # Llista tasques programades
crontab -r                               # Elimina totes les tasques

# Sintaxi:
# ┌───────────── minut (0-59)
# │ ┌───────────── hora (0-23)
# │ │ ┌───────────── dia del mes (1-31)
# │ │ │ ┌───────────── mes (1-12)
# │ │ │ │ ┌───────────── dia de la setmana (0-7, 0 i 7 = diumenge)
# │ │ │ │ │
# * * * * * comanda_a_executar

# Exemples:
0 14 * * * echo "Hola" >> ~/log.txt      # Cada dia a les 14:00
*/5 * * * * /home/usuari/script.sh       # Cada 5 minuts
0 0 * * 0 backup.sh                      # Cada diumenge a mitjanit
```

### `systemctl`
Gestiona serveis del sistema (systemd).
```bash
systemctl status ssh                     # Estat d'un servei
sudo systemctl start ssh                 # Inicia un servei
sudo systemctl stop ssh                  # Atura un servei
sudo systemctl restart ssh               # Reinicia un servei
sudo systemctl enable ssh                # Activa a l'arrencada
sudo systemctl disable ssh               # Desactiva de l'arrencada
```

### `journalctl`
Visualitza registres del sistema.
```bash
journalctl -u ssh                        # Reg
