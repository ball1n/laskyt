# H4 Omat komennot

Tehtävä on suoritettu Virtualboxiin asennetulla Debian käyttöjärjestelmällä. Tehty 5.12.2022, apuna Teron tunti opetus ja muiden opiskelijoiden muistiinpanot. 

Aikajanat ja komennot ei ole aivan linjassa, koska olen tehnyt tehtävän useaan otteeseen kun olen taistellut screenshotin kanssa. Voin iloksenne kertoa, että minun ongelmani oli se, että repositoryn nimestä puuttui ".md". Ja siis tähän meni 6h, että vika löytyi.

## a) Hei komento! Tee järjestelmään uusi "hei maailma" -komento ja asenna se orjille Saltilla. Liitä raporttiisi orjan 'ls -l /usr/local/bin/' tulosteesta   ainakin se rivi, jolla näkyy uuden komentotiedostosi oikeudet.

Aloitan tekemällä uuden kansion ja tekemällä tekstitiedoston sinne "micro eka.sh"

    $ mkdir uusimaa

![image](https://user-images.githubusercontent.com/117892213/205673214-cd3f50ea-dd8b-40a9-9836-93f53f754760.png)

Tämän jälkeen on hyvä testata toimiiko komento "eka.sh", jos ei niin tarkista oikeudet ja tarvittaessa anna ne
![image](https://user-images.githubusercontent.com/117892213/205674085-afdde15d-5721-418f-9885-c34d73225e78.png)


    $ chmod ugo+x eka.sh

Tämän jälkeen komento "eka.sh" toimi.

Lisäsin tiedoston kopioimalla sen komennolla 

    $ sudo cp eka.sh /usr/local/bin

Ja kävin tarkistamassa, että se on siellä ja sen oikeudet, ylhäällä kerrotulla tavalla.

Tämän jälkeen kun komento toimii käsinajettuna, automatisoin sen Saltilla.

![image](https://user-images.githubusercontent.com/117892213/205674442-4cc109b3-6e70-4b99-88f1-f9b8718f8b93.png)

Siirryn salt kansioon, tässä kuvassa on jo kopioitu tiedosto valmiiksi mutta sen pystyy tehdä seuraavalla komennolla

    $sudo cp uusimaa/ /srv/salt

Kun init.sls tiedosto on valmis voi testata toimivuutta, itse menen ja poistan tiedoston /usr/local/bin kansiosta
   
![image](https://user-images.githubusercontent.com/117892213/205675127-0689df54-f2b3-4777-8e76-e71fd0557b2a.png)

Tämän jälkeen ajan komennon saltilla
    
![image](https://user-images.githubusercontent.com/117892213/205675641-f128bf56-f523-4ba9-80dc-a7cc1611a888.png)

Ja se toimii, kun tiedosto löytyy uudestaan, oikeilla oikeuksilla /usr/local/bin kansiosta

# b) whatsup.sh. Tee järjestelmään uusi komento, joka kertoo ajankohtaisia tietoja; asenna se orjille. Vinkkejä: Voit näyttää valintasi mukaan esimerkiksi päivämäärää, säätä, tietoja koneesta, verkon tilanteesta...


