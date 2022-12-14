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

As told in the quide, Discord can't be found from the default system repository of Debian and need's to be downloaded manually as Deb binary from the [official wesbite](https://discord.com/download). And with the next command on my terminal, you don't need to visit the Discord website.

Well, I could remove the text above but I'm going to leave it there as it did not work for me and after reading few other ways to install Discord, it looks like using Snap, is the most popular and easiest way of doing it. Snap is a packaging and deployment system software for OS that use Linux kernel.

So [this](https://www.linuxcapable.com/how-to-install-discord-on-debian-11-bullseye/) is my quide to follow now.
It start's the same as the first one, need to update&upgrade and then I can install Snap.

![image](https://user-images.githubusercontent.com/117892213/207586666-bbef2120-2361-4fe7-89a3-9a2f9d3ea495.png)


