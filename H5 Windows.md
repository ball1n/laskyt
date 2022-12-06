## H5 Windows
Tehtävä on osa Tero Karvisen kurssia, Palvelinten hallinta. Kurssin sivulle löytyy linkki sivun alhaalta.

Tehtävä on toteutettu Windows 11, joka on raudalla ja Virtualboxin avulla pyörivällä Debianilla. Tehty 6.12.2022.

# a) Hello Window Salt! Tee Windowsille SLS-tiedostoon Salt-tila, joka tekee tiedoston nimeltä "suolaikkuna.txt".

Tähän tehtävään tarvitsee asentaa Saltv, itse latasin tunnilla jo täältä: https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/windows.html

Kun tiedosto on ladattu, avaan Powershellin järjestelmänvalvojana. 

![image](https://user-images.githubusercontent.com/117892213/205885181-0d707a15-ee9d-4ee1-ade5-ece19d7bce6e.png)

Siirrytään hakemistoon mihin tiedosto latautuu, itselläni löytyy

    C:/User/olive/Downloads ./Salt-Minion-3004.2-1-Py3-AMD64-Setup.exe 

Olen ladannut Salt:in tunnilla, joten en suorita sitä uudestaan mutta tämän jälkeen vain pitää painaa next:iä muutamia kertoja ja Salt on asentunut koneelle.

Testaan onko itselläni vielä toimiva Salt koneella, komennolla "echo oliver"

   ![image](https://user-images.githubusercontent.com/117892213/205886384-72a7ba98-40b8-45da-99c0-93efe725fad2.png)

Toimii. 

Teen ensiksi polun, jota tulen käyttämään init.sls teksti-komennon polkuna. 

![image](https://user-images.githubusercontent.com/117892213/205889436-6a93760e-99a2-4d23-9b4e-0bfa04de1c43.png)


Sen jälkeen luon polun mikä näkyy kuvassa ja teen init.sls tekstitiedoston

![image](https://user-images.githubusercontent.com/117892213/205888942-82e2a0c3-8e6d-4dfc-81d0-7ecb2dde1cd0.png)

init.sls tiedoston sisältö

![image](https://user-images.githubusercontent.com/117892213/205889822-7e68aaf3-ed42-48c7-87fa-06821ae8cb37.png)

Tämän jälkeen ajan Saltilla tiedoston, tunnilla tätä käsiteltiin ja tämä piti ajaa jostain syystä tällä tavalla. Kopioin suoraan esimerkistä minkä Antti Halonen näytti.

![image](https://user-images.githubusercontent.com/117892213/205890401-00d8d2c5-34e0-4e43-b1f8-a15d1008941d.png)

Tarkistetaan vielä haluttu lopputulos Temp kansion sisältä

![image](https://user-images.githubusercontent.com/117892213/205890555-340ccdd8-a776-4f43-8716-7a9286b4d541.png)

Haluttu lopputulos saavutettu.


# Lähteet:

- https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/
- https://github.com/miljonka/Palvelinten-hallinta/blob/main/h5_Windows.md
- https://github.com/sannnir/h5-Windows
- https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/windows.html
- https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax


