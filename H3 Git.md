# H3 Git
a) MarkDown. Tee tämän tehtävän raportti MarkDownina. Helpointa on tehdä raportti GitHub-varastoon, jolloin md-päätteiset tiedostot muotoillaan automaattisesti. Tyhjä rivi tekee kappalejaon, risuaita ‘#’ tekee otsikon, sisennys merkitsee koodinpätkän.

- Aloitin tehtävän tekemällä uuden varaston nimeltä "laksyt", johon tulen jatkossa lisäämään kurssin läksyt. Varastoon lisäsin uuden markdown tiedoston.

b) Offline. Tee paikallinen offline-varasto git:llä. Varaston nimessä tulee olla sana "cat" (kissa). Aiemmin tehty varasto ei siis kelpaa. Aseta itsellesi sähköpostiosoite ja nimi. Näytä varastollasi muutosten teko ja niiden katsominen lokista.

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
