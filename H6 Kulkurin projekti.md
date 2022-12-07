## H6 Kulkurin Projekti

# x) Lue ja tiivistä (muutamalla ranskalaisella viivalla per artikkeli, poimi esim itsellesi keskeisimmät komennot)

# Karvinen 2017: Vagrant Revisited – Install & Boot New Virtual Machine in 31 seconds (Suosittelen käyttämään tässä koneena 'vagrant init debian/bullseye64')

- Artikkeli käsittelee Vagrantin asennuksen ja käynnistämisen.

    $ vagrant init bento/ubuntu-16.04 (debian/bullseye64, omassa käytössä)
    $ vagrant up
    $ vagrant ssh

# Karvinen 2021: Two Machine Virtual Network With Debian 11 Bullseye and Vagrant

- Artikkelissa käydään läpi, miten tehdään kaksi virtuaalikonetta samaan aikaan. Keskeisin itselleni on Vagrantfilen scripti. 

# Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux

- Kuten artikkelin otsikossa mainitaan niin nopea aloitusopas Salt Masterin ja Slave:n pariin. Miten asentaa ja käyttäänottaa.

    master$ sudo salt '*' cmd.run 'whoami'
    tero:
     root
     
Tärkeää, että Master käyttäjä on selvillä ja tiedät itsekin mikä käyttäjä se on, varmaan helppo mennä sekaisin jos hallitsee useita koneita.

# a) Hello Vagrant. Asenna virtuaalikone Vagrantilla.

- Minulla oli jo asennettuna valmiiksi tunnilla omalle Windows 11 läppärille Vagrant, jonka latasin tältä sivulta: https://developer.hashicorp.com/vagrant/downloads
Tehtävät on tehty Powershellillä.

Aloitan tehtävän tekemällä ensiksi uuden kansion, jonka jälkeen siirryn kansioon jossa annan komennon "vagrant init debian/bullseye64"

![image](https://user-images.githubusercontent.com/117892213/206147609-814e7099-7fc3-4b39-ac33-5b6cef53637a.png)

Samalla komento luo "Vagrantfilen" valmiiksi ja täten olen valmis käynnistämään koneen ja yhdistämään siihen.

    $ vagrant up

Käynnistää koneen luomis prosessin ja tämä on lopputulos, ensiksi powershelliltä ja vikana VB:lta kuvat.

![image](https://user-images.githubusercontent.com/117892213/206148550-171d8848-22cc-456f-89cd-342aaa8de697.png)

![image](https://user-images.githubusercontent.com/117892213/206148617-4e482506-f277-4cf0-bcd8-e20f65fc2216.png)

Ja lopuksi vielä yhteys koneeseen "vagrant ssh" varmistaakseni yhteyden toimivuuden.

![image](https://user-images.githubusercontent.com/117892213/206148872-e8449efe-3df8-4523-a84e-fb510bb0d2c6.png)


# b) Yksityisverkko. Asenna kaksi virtuaalikonetta samaan verkkoon Vagrantilla. Laita toisen koneen nimeksi "isanta" ja toisen "renki1". Kokeile, että "renki1" saa yhteyden koneeseen "isanta" (esim. ping tai nc). Tehtävä tulee siis tehdä alusta, vaikka olisit ehtinyt kokeilla tätä tunnilla.

Aloitan tehtävän tekemällä uuden kansion mihin itse teen "Vagranfilen", lisää Vagrantilfeen Teron artikkelista: https://terokarvinen.com/2021/two-machine-virtual-network-with-debian-11-bullseye-and-vagrant/ scriptin, johon muutan tietokoneiden nimet, tehtävän mukaiseksi. 

![image](https://user-images.githubusercontent.com/117892213/206161413-942385bd-b9ba-46c8-be95-4aa1ebbf9eb9.png)

Tämän jälkeen voimme aloittaa koneiden luomisen. Vagrantfile pitää muuttaa .exe muodosta pois kuvassa näkyvällä tavalla ja sitten pamauttaa komento

    $ vagrant up

![image](https://user-images.githubusercontent.com/117892213/206162557-13ae9ab5-5037-4c4c-92bd-e307072d8471.png)

Näin on syntynyt kaksi uutta virtuaalikonetta VB:lle

![image](https://user-images.githubusercontent.com/117892213/206162759-f248441c-be0a-437b-b5d1-6f7cfdad5ca5.png)

Seuraavaksi kokeillaan yhteyttä koneiden välillä. Kirjaudutaan "vagrant ssh" komennolla ja pingataan toista konetta.

isanta IP osoite: 192.168.88.101
renki1 IP osoite: 192.168.88.102

Nämä on määritelty Vagranfilen scriptissä.

![image](https://user-images.githubusercontent.com/117892213/206163819-64db6dcc-f109-451c-95c4-a020b6652729.png)

![image](https://user-images.githubusercontent.com/117892213/206164133-0dcbc899-0aa0-4e05-8c4c-44eca32dae75.png)

Molemmat toimii, tässä kohtaa huomaan, että ongelmaksi on tullut tunnilla asennetut "too1" ja "too2" koneet, joilla on aivan samat asetukset kuin "isanta" ja renki". Poistan tunnilla tehdyt koneet.

Asia ei ollutkaan niin simppeli. En ole ollut huolellinen Vagrantfilen kanssa ja muuttanut nimiä tarpeeksi huolellisesti vaadittuihin. Korjaan virheeni ja luon koneet uudestaan. Kokeilen pingaukset uudelleen.

![image](https://user-images.githubusercontent.com/117892213/206166057-d4d22a09-4181-4e13-95d2-dedd1196d979.png)

Noin nyt näyttää paremmalta ja oikealta. 

# c) Salt master-slave. Toteuta Salt master-slave -arkkitehtuuri verkon yli. Aseta edellisen kohdan kone renki1 orjaksi koneelle isanta.

Tehtävän aloitan lataamalla Salt master-slave arkkitehtuurin oikealle koneelle. 

    vagrant@isanta:~$ sudo apt-get install salt-master 
    vagrant@renki1:~$ sudo apt-get install salt-minion
    
Kun Salt arkkitehtuuri on asennettu, menen renki1 koneella antamaan "minion" tiedostolle isanta koneen IP-osoitteen, jotta kone tietää kuka on sen master-kone.

![image](https://user-images.githubusercontent.com/117892213/206171285-f83457b3-d551-4162-8626-0a20be5926d8.png)

Käynnistän salt-minionin uudestaan

![image](https://user-images.githubusercontent.com/117892213/206171482-984a0361-7069-484e-b122-9b7b06a364c5.png)

Siirryn master koneelle ja tarkistan onko renki1 avain pyyntö tullut sinne. 

![image](https://user-images.githubusercontent.com/117892213/206171981-1e5ddd43-0744-45a8-85a5-ceac405af1d9.png)

    $ sudo salt-key

Näyttää tilanteen 

    $ sudo salt-key -A

Antaa luvan, en testannut onko kyseessä oikea vaan luotin, että kukaan ei ole päässyt tässä välissä tekemään mitään selkäni takana.

Nyt voin testata toimiiko yhteys orjan kanssa

    $ sudo salt '*' test.ping
    $ sudo salt '*' cmd.run "hostname"

![image](https://user-images.githubusercontent.com/117892213/206172736-128e69c2-5009-428e-a126-00ac5d180dee.png)


Homma toimii kuten pitää.

# d) Oma suola. Tee ensimmäinen työversio projektistasi. Miniprojektilla tulee olla jokin tarkoitus, vaikka se olisi keksitty. Projektilla tulee olla sivu (esim. Github, Gitlab...), josta selviää projektin perustiedot. Toiminnallisuutta tulee olla kokeiltu, mutta sen ei tarvitse olla valmis. Valmiit projektit esitellään viimeisellä tapaamiskerralla. Tässä tehtävässä palautettava työversio ei siis ole vielä lopullinen.

   


