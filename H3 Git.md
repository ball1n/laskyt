# H3 Git
## a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.
[![https://imgur.com/ZIYS0vS.png](https://imgur.com/ZIYS0vS.png)](https://imgur.com/ZIYS0vS.png)
- Aloitin tehtävän tekemällä uuden varaston nimeltä "laksyt", johon tulen jatkossa lisäämään kurssin läksyt. Varastoon lisäsin uuden markdown tiedoston.

## b) Offline. Tee paikallinen offline-varasto git:llä. Varaston nimessä tulee olla sana "cat" (kissa). Aiemmin tehty varasto ei siis kelpaa. Aseta itsellesi sähköpostiosoite ja nimi. Näytä varastollasi muutosten teko ja niiden katsominen lokista.

- Teen ensimmäiseksi kansion komennolla

    $ git init miksicat

Siirryn kansioon

    $ cd miksicat/

Teen markdown tiedoston README.md

    ~/miksicat$ micro README.md

Tämän jälkeen suoritan komennot

    ~/miksicat$ git add .

    ~/miksicat$ git commit
  
Ja saan tuloksen 

    [master (root-commit) a533d65] Add README.md
     1 file changed, 1 insertion(+)
    create mode 100644 README.md
 
 Lokien tarkistaminen
 
    oliver@heroic:~/miksicat$ git log --patch
    commit a533d65a418ced581d7360c15854ad71ce3d0fc5 (HEAD -> master)
    Author: Oliver Santasalo <oliversantasalo@gmail.com>
    Date:   Fri Nov 11 16:14:05 2022 +0200

    Add README.md

    diff --git a/README.md b/README.md
    new file mode 100644
    index 0000000..be34975
    --- /dev/null
    +++ b/README.md
    @@ -0,0 +1 @@
    +Toimiiko?

## c) Doh! Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset --hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

- Käyn kirjoittamassa README.md tiedostoon ja sen jälkeen suoritan komennon

     $ git reset --hard
 
jolloin saan 
 
    HEAD is now at a533d65 Add README.md
    oliver@heroic:~/miksicat$ cat README.md 
    Toimiiko?
 
Eli teksti minkä lisäsin ja tiedosto palasi aikaisemmin toimineeseen vaiheeseen. Olisin toki voinut näyttää mitä lisäsin, koska nyt voi epäillä minun luotettavuuttani.  

## d) Online. Tee uusi varasto GitHubiin (tai Gitlabiin tai mihin vain vastaavaan palveluun). Varaston nimessä ja lyhyessä kuvauksessa tulee olla sana "car" (auto). Aiemmin tehty varasto ei kelpaa. (Muista tehdä varastoon tiedostoja luomisvaiheessa, suosittelen tekemään README.md ja vapaista lisensseistä itse tykkään GPLv3 eli GNU General Public License, version 3)

Teen uuden varaston nimeltä "carjack" ja annan sille lyhyen kuvauksen. 
Lisään README.md kansion sekä GPL 3.0 lisenssin.

## e) Dolly. Kloonaa edellisessä kohdassa tehty varasto itsellesi, tee muutoksia, puske ne palvelimelle, ja näytä, että ne ilmestyvät weppiliittymään.

Kloonaan "carjack" varaston komennolla

       $ git clone git@github.com:ball1n/carjack.git
       
Siirryn kansioon

       $ cd carjack/
       
Avaan tiedoston README.md

       ~/carjack$ micro README.md
       
Tältä githubini näyttää nyt (opin miten otan screenshotin myös)

![image](https://user-images.githubusercontent.com/117892213/201364044-2dedb84d-8d06-4824-be2a-a5bb05eb51b4.png)

Tämän on muutos README.md tiedostoon

![image](https://user-images.githubusercontent.com/117892213/201364213-42358660-a89a-4299-b063-9e582e3b0122.png)

Sen jälkeen pusken ne palvelimelle seuraavalla komennolla

       ~/carjack$ git add . && git commit; git pull; git push
      
ja lopulta kuva muutoksista

![image](https://user-images.githubusercontent.com/117892213/201364711-04f204e5-2319-4951-bec8-92863f478cd2.png)

## Haluaisin vielä yrittää tehdä vapaaehtoisia tehtäviä ja katson jos palaan myöhemmin niiden pariin, nyt on kuitenkin perjantai

## Lähteet

- https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/
- https://terokarvinen.com/2012/git-from-offline-to-network/
- https://www.wikihow.com/Take-a-Screenshot-in-Linux
