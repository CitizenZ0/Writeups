  GNU nano 2.9.3                                                                                                                      README.md                                                                                                                                

# CTF Writeup for 'Misc/Guessy Discord flag???' (DarkCTF)

.

.

#### Challenge Information:


Title: **Misc/Guessy Discord flag???**
Description: Find the Flag on discord. Good Luck xD [Discord LINK]
Author: White_Wolf




The challenge is a Misc task and the only thing we have to do is find the flag on the DarkArmy (Creator of the DarkCTF) Discord Server.

The first thing i did is searching for 'CTF' and 'darkCTF' with the discord search function to maybe find some flags, but no.
Then i checked pinned messages and Channel description but there was nothing.

I remembered that almost every service has an API were you can get more informations about a Server/Username or whatever.
Discord has one too (https://discord.com/api/*) Heres the Documentation: https://discord.com/developers/docs/intro
Theres is an endpoint were we can get more detailed informations about the server itself. (https://discord.com/api/guilds/[SERVER_ID])


So now we only have to get the Server Id but that is easy, we only have to activate Developer Mode in the Discord Profile (Go to Settings/Appearnce and then activate Developer Mode) Now we can simply get the server ID by right click on the Server Name and click 'Copy ID$


Now we go to https://discord.com/api/guilds/[SERVER_ID] but:

![Picture](https://i.imgur.com/5jLZx0L.png)


Thats because we didnt send any authorization headers to the server.
When we use discord, we use the 'authorization' and 'x-super-properties' header for every action. Normaly it is sended when we use discord but not when we use the api manually.

Now in order to use this api endpoint we need to send it with the request.
I use ModHeader (A chrome addon for manipulating headers)

Then i send the request and we get more detailed informations about the server and i found the flag:

![Picture](https://i.imgur.com/2SQlRWI.png)


We know that the flag format is 'darkCTF{}' so i just changed it a bit and solved the challenge.

(The flag was just a emojie name so it could be much much simpler)



**Writeup written by CitizenZ**



