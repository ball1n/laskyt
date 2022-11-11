## a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.
## b) Offline. Tee paikallinen offline-varasto git:llä. Varaston nimessä tulee olla sana "cat" (kissa). Aiemmin tehty varasto ei siis kelpaa. Aseta itsellesi sähköpostiosoite ja nimi. Näytä varastollasi muutosten teko ja niiden katsominen lokista.
    $ git init miksicat
    $ cd miksicat/
    ~/miksicat$ micro README.md
    [master (root-commit) a533d65] Add README.md
    oliver@heroic:~/miksicat$ git log --patch
    commit a533d65a418ced581d7360c15854ad71ce3d0fc5 (HEAD -> master)
    Author: Oliver Santasalo <oliversantasalo@gmail.com>
    Date:   Fri Nov 11 16:14:05 2022 +0200
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