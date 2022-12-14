## Project: Learning the basic's

I want to make a Salt module that will set up for a fresh computer two of my favourite desktop applications: Discord and Spotify. This project is last homework for Configure Management Systems Course from Tero Karvinen, [link to the course site](https://terokarvinen.com/2022/palvelinten-hallinta-2022p2/)

I'm doing the project with VirtualBox run Debian 64-bit.
My plan is to test the configured init.sls YAML, on my other virtual computer's and confirm that way, it works.

# Start of the project

First I needed to research how this is done and what kind of technical problems I might encounter. As I did not have the full picture of how this project would be done, in my head yet. I used as my help project's, done previously on Tero's same course, [link to the previous course's](https://terokarvinen.com/search/?q=palvelinten+hallinta). The most usefull for me was done by [Justus](https://github.com/Justus-stack/h7_moduli/blob/main/report.md).

# The beginning

I started the project first installing myself both Discord and Spotify to get all the right paths and informations, that I need for my init.sls file.

# How I installed Discord

I followed [this](https://www.how2shout.com/linux/3-ways-to-install-discord-on-debian-11-bullseye-linux/) quide on how to install Discord on Debian. 

![image](https://user-images.githubusercontent.com/117892213/207582915-32216953-1b41-42a7-9b33-55b8c1f8cfb6.png)

As told in the quide, Discord can't be found from the default system repository of Debian and need's to be downloaded manually as Deb binary from the [official wesbite](https://discord.com/download). For me the command did not work, so I downloaded it manually from the Discord website and then installed it. 

![image](https://user-images.githubusercontent.com/117892213/207590912-fdce5470-773b-4608-bec4-2cdcdb493d71.png)

After that, I had the app on my Debian.

![image](https://user-images.githubusercontent.com/117892213/207591408-c0914e91-93db-4685-86bc-b4008b88ee78.png)

# How I installed Spotify

For this I googled basically how to install Spotify for Debian and got simple instructions from Spotify's own [website](https://www.spotify.com/fi/download/linux/).

First I configured debian repository

    $ curl -sS https://download.spotify.com/debian/pubkey_5E3C45D7B312C643.gpg | sudo apt-key add - 
      echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
      
    $ sudo apt-get update && sudo apt-get install spotify-client  
    
![image](https://user-images.githubusercontent.com/117892213/207593404-7d92de40-2614-410d-9ac0-97abcf92f924.png)

And there we go, now both Spotify and Discord have been installed to my Debian succesfully. Now I will start working the init.sls.

# Hard part of the project

I started making a new directory to /srv/salt and then creating init.sls file with "sudoedit". First I'm going to add Salt command for Spotify to the init.sls file

![image](https://user-images.githubusercontent.com/117892213/207595568-cbe8e122-5973-4409-bcee-883985ffa29d.png)

I had to use now help from [Justus project](https://github.com/Justus-stack/h7_moduli/blob/main/report.md) to get the YAML for my init.sls file. I though needed to edit the path for the key and list. List was found from **/etc/apt/sources.list.d** and key's were found at **/etc/apt/trusted.gpg.d**.
Easy way for me to find the key was with the help of [Jesperi Kuula's homework](https://jesperikuula.wordpress.com/palvelinten-hallinta-viikko-4/)
I found from there a command,

    $ sudo apt-key list
    
And with this it was easy to find the right key for Spotify.

![image](https://user-images.githubusercontent.com/117892213/207598379-0bb54c57-e1ca-442d-b2ae-fdc769e0f4ab.png)

I will go add this to my init.sls. And this is the aftermath.

![image](https://user-images.githubusercontent.com/117892213/207599173-c17f5504-9a96-41fd-915f-8022a4d59b58.png)

Also you need to copy them to the /srv/salt/project file, like this.

![image](https://user-images.githubusercontent.com/117892213/207603709-841b29c1-d60d-48ab-b04c-9714377c591f.png)

Now I can test, if it works.

![image](https://user-images.githubusercontent.com/117892213/207604051-ff7c59b1-c1ac-4fde-a56c-af16c6eed4ad.png)

And there we go. Spotify is added, now I move to take care of Discord.

First I will start with editing init.sls file and with the help of [Justus, again.](![Uploading image.png…](https://github.com/Justus-stack/h7_moduli/blob/main/report.md)
I edit my path, where I downloaded by going to Firefox and copying from the link at downloads the right path.

![image](https://user-images.githubusercontent.com/117892213/207612677-184edb0e-6523-4897-b775-4b9aa72beb89.png)

This is how it looks like and after trying to run it on salt-call, it does not work. I'm getting this message.

![image](https://user-images.githubusercontent.com/117892213/207612958-afe6cf6f-45fe-4be5-974a-ef1db194be33.png)













    
    
