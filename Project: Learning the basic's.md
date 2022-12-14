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








    
    
