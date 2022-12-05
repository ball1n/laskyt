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

Tämä tehtävää tehdään aikalailla samalla tavalla kuin aikaisempi mutta init.sls tiedostoon ja whatsupp.sh ovat hieman poikkeeavia. 

Aloitan tekemällä uusimaa/ kansioon uuden tiedoston nimeltä "whatsupp.sh" ja lisään sinne kuvassa näkyvät komennot.

![image](https://user-images.githubusercontent.com/117892213/205684725-b4fffb12-142c-4103-a6e5-001f4d71059e.png)

Komento näyttää päivämäärän ja kellonajan.

Suoritan seuraavat vaiheet

![image](https://user-images.githubusercontent.com/117892213/205685190-a5115b6a-30cd-4134-9911-82d8ef8c197e.png)

Lisään init.sls tiedostoon whatsapp.sh:lle komennon samoilla oikeuksilla kuin eka.sh:lla.

![image](https://user-images.githubusercontent.com/117892213/205685642-d2016673-5086-4846-9ae4-a53ecf523a35.png)

Teen testin ennen ja jälkeen salt komentoa

![image](https://user-images.githubusercontent.com/117892213/205686007-23366d6b-a524-4cf1-8784-382a059eac90.png)

Kaikki toimii kuten pitääkin.

# c) hello.py. Tee järjestelmään uusi komento Pythonilla ja asenna se orjille. Vinkkejä: Hei maailma riittää, mutta propellihatut saavat toki koodaillakin. Shebang on "#!/usr/bin/python3". Helpoin Python-komento on: print("Hei Tero!")

Sama idea kuin aikaisemmissa tehtävissä, joten lisään tiedoston suoraan /srv/salt/uusimaa kansioon ja syötän shebangin tekstitiedostoon. Tämän jälkeen annan tiedostolle tarvittavat oikeudet "sudo chmod ugo+x hello.py". Testaan myös komennon.

![image](https://user-images.githubusercontent.com/117892213/205687170-2c7e9418-7626-4dbc-a8ad-714908ab90ce.png)

Kun komento toimii siirryn init.sls tiedostoon ja lisään sinne komennon joka antaa oikeudet hello.py tiedostolle.

![image](https://user-images.githubusercontent.com/117892213/205687417-2cf0aee4-1e26-4a1b-84ef-760e42f9c280.png)

Testataan taas ensiksi komentoa hello.py ja saltin jälkeen uudestaan.

![image](https://user-images.githubusercontent.com/117892213/205688151-b2fb43d1-ee4d-4cc4-9775-7535e9f6102e.png)

Sama lopputulos kuin B tehtävässä, homma pelittää kuin juuri öljytty Lada.

# d) Laiskaa skriptailua. Tee kansio, josta jokainen skripti kopioituu orjille.

Eli tehtävän ideana on automatisoida komentojen tekeminen.
Aloitan luomalla uuden kansion /srv/salt/uusimaa sisälle nimeltä "komennot", sen jälkeen siirrän a,b ja c tehtävissä tehdyt komennot kansioon

![image](https://user-images.githubusercontent.com/117892213/205690460-4b0574c8-3494-445e-8726-893e94a91b03.png)

Kun tiedostot ovat siirretty ja kansio tehty, palataan init.sls tiedoston kimppuun ja muokataan se osoittamaan oikeaan paikkaan ja vaihdetaan komennot recursiviksi. 

![image](https://user-images.githubusercontent.com/117892213/205691993-db56942a-7841-4cc5-aeed-d5423992a307.png)

Käyn poistamassa komennot

![image](https://user-images.githubusercontent.com/117892213/205691894-d7b99cc1-b228-402d-a541-8a86cd12972b.png)

Aloitetaan testaaminen

![image](https://user-images.githubusercontent.com/117892213/205692213-4927f663-cfbb-4659-9bf8-078772fd78e6.png)

Ajetaan saltilla komento

![image](https://user-images.githubusercontent.com/117892213/205692671-3357aa07-1d48-4f0b-a3cd-c4dc0a72535e.png)

Korjataan samalla typo init.sls tiedostosta :D

![image](https://user-images.githubusercontent.com/117892213/205692795-dbb5ed9e-803d-4646-aff5-e331f74c2a3e.png)

Ja kaikki skulaa

# Lopetan tehtävän tähän, toivottavasti palaan vielä tai jos aika ei salli niin siirryn H5, kun olen jo muutenkin aivan liikaa jäljessä. Oma vika

## Lähteet:

- https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/
- https://github.com/sannnir/h4_OmatKomennot
- https://github.com/miljonka/Palvelinten-hallinta/blob/main/h4_Omat%20komennot.md
- https://github.com/therealhalonen/configuration_management_systems/blob/master/h4/report.md

Kiitos opiskelijoille hyvin tehdyistä raporteista niin sain itseni vielä mukaan ja muistutettua miten tehtävät menikään!
