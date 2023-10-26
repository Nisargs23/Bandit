# Writeups
## Level 0
I started with overthewire bandit feeling a little clueless but it got easier to understand pretty soon.
Level 0 was useful to understand the usage of the ssh command which provides communication over a network.
<img width="578" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/6a16ca6a-245b-4491-8023-4ba8db48af9a">

Level 0 was pretty straightforward as you had already shown us the basics.

<img width="257" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/767b04a7-7933-47d8-a4e2-dc6a170ff98b">

Then I used the ls and cat commands to access the file and read it.
## Level 1
The next task was to open a file called '-'. 

Of course I tried to simply open the file using cat but it didn't work.Nothing happened infact. It didn't even give an error or anything.
It wasn't too difficult to solve though. A simple google search and the links provided on the level 1 page offered the solution.
I learned that the - character is used before entering commands and hence a command is expected further. To get around this issue we need to use ./ before the filename.

<img width="267" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/13e66453-1f17-49cd-a174-deb9690a1a16">

## Level 2
Using the password in level 1 I went on to the next level. There was a file called spaces in this filename.
I went through few of the man pages and read about the cd command. And as the question specifically mentioned home directory, I tried to use the cd command. That didn't work though. I went through the helpful reading material thing and it gave the solution. 
Though I think I should have guessed the issue by looking at the filename.
Anyways the spaces were the issue and I found that it was treating all the words as different names instead of a whole filename. I could access the file by putting the filename in double quotes. Another thing that can be done is using the \ before each character.

<img width="386" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/905510a9-9663-4c2b-a8f0-58b0b73eff2e">

## Level 3
Now I logged in again and used ls to see inhere written in blue. As the question said inhere directory I assumed it was a directory and used the cd command. This got me into the directory. Then I used ls again but there was no result.
Now as the question said hidden file, I made a google search on how to see hidden files in a directory. The first result said that to see the hidden files we can use -a after the ls command. 
This enables all the files to be seen. 
It worked and I saw the .hidden file. It was accessible by using cat.
So in this level i learned to access a directory and also see files that are hidden. 
I also googled how to exit an entered directory incase i needed to go back out. I found I can simply use cd.

<img width="295" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/78418825-61c8-4d0d-9948-534a61b611f1">

## Level 4
This level took me quite some time.
I logged in and did the usual stuff. ls and cd command to get into the directory. There were a bunch of files and i tried opening one of them.
It had gibberish in it. Well at least gibberish to me. So i guess that's what human unreadable means.
I used the man page for 'file' as it said that file command can determine the file type.
There were several variations for the file command and I tried quite a few of them but they all pretty much gave the same output. And the different ones didn't make sense.

<img width="606" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/ac2a2d3e-ecbf-4e50-bf28-929a00f656e9">

So i just googled how to see the file type and it said that file * would give the file types of the files in the active directory. But that didn't work again.
I messed around quite a bit but couldn't get it to work. So I opened the walkthrough thing. Sure enough he used the file *. 
I didn't realise that it wasn't working beacuse all the files started with a - sign.
I learned that it would work if I used ./ before the *. So it finally worked. There was only one with ascii text and i knew that data meant gibberish as i already tried to open file00.

<img width="378" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/fc30484c-bfa6-451f-8efd-cc71e826ef97">

lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
## Level 5

Similar to the last level there is an inhere directory which i accessed. There were just a bunch of other directories. I tried using the find ./* thing like the last level but it gave a lot of files. 

<img width="929" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/9cee9c76-4a99-45a0-a533-c1e1c7a071bf">
<img width="245" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/f919464a-6fd0-4367-b7a2-beb4da20ecab">


So now I searched the man page for find. I found a readable command. It worked but too many files. 

Then I found the size command on the same page. Took me a while to figure out the syntax of the size parameter. I had to make a few google searches but I got it. The c went after the 1033. This worked too but too many files again.
Now there was an executable command but I couldn't find anything about not executable. So back to google. I found the \! prefix on some website and it seemed to work. 

<img width="299" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/794b4c0b-1205-4ff7-a451-d8b2c2cb69be">


Now the problem was that the parameters I was setting seemed to work but that wasn't narrowing down anything. It was only when I saw one of the examples on the man page that I realised that all of them work together. In hindsight that made sense as you would need to set different parameters to find a file. Anyways it worked after a while.

<img width="491" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/9c84295c-f2fa-4eb8-992f-399589d03cc2">

P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Level 6
Some new parameters in this level, and the size one is already known. It was easy enough to find the user and group commands on the man page for find. They had pretty simple syntaxes.

Honestly, I thought "that was pretty quick". Until I used the command. No result. Oh yeah, I didn't change the directory.
So ls. Only this time no directory. ls -a . Still no directory, but there were some names which made no sense and gave a bunch of gibberish on trying to access it. 
So I read the question again, and it said the whole server.
On searching on google, I learned that for a specific directory, you can just use find /directory instead of shifting to the directory first. This was of no use for this particular level though as the file wasn't in any diretory. And simply specifying the conditions without any directory didn't seem to work. So something was missing.

It had to be find / instead of just find.

<img width="624" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/76bd9fdf-1eec-4467-9819-27040a4782d7">

Well it worked. Kind of. There were a whole bunch of permission denied. One of the files stood out on closer inspection but that didn't seem like a very efficient way to find the file. So I googled the question. It led me to a command 2>/dev/null.
This made absolutely no sense. So I tried to find something else that I might unserstand but I found only this to hide the denied permissions. 
So I tried it and sure enough, the correct file was the only one displayed.

<img width="544" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/4025ad5c-d2e9-4f7b-9d21-23af39f7aef6">

z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
## Level 7

For this level there was a file name and the word next to it.
On using ls, there was only one file, data.txt.
When I tried to see the contents, it just kept going. So obviusly, I had to find the word 'millionth' from data.txt

<img width="242" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/71d16723-ab84-45be-8a58-16902a54eb82">

I quickly went through the man page for grep. I looked for examples, but there was only one example, which was a little complicated for me. So I just googled the syntax for a basic grep command. Et voila, there was the word and the password next to it.
This one took lesser time than the previous 2 levels. 
I learned how to look for a word in a particular file in this level.

<img width="361" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/1f3e4a13-8adf-4ff8-95e5-57fd881c4456">

TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Level 8

In this level , the password was in the line that appeared only once. In the 'commands you may need' section, I saw uniq which seemed like an obvious choice.
I used uniq but it pretty much gave the same text again. The man page said that it only filters adjacent matching lines so I would have to sort this too. The sort command worked. I confirmed with a google search that uniq is usually used with sort.

<img width="239" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/7b754e06-4476-4468-853e-3dd0e94896fb">

Now how would both of them work together? I googled and there were these commands with '|'. Then I read that piping and redirection page from helpful reading material. 

I learned that > is used to send data to a particular file. This made 2>/dev/null a little bit easier to understand. I also learned what piping is. It is basically sending data after a command is performed to another command.
Now back to the problem at hand, I tried the few variations of uniq like -c. Without sorting there were a lot of lines that occurred only once but that was because they weren't adjacent. 

<img width="302" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/b0fbe505-093f-4ff7-ae44-5511772ee95b">

So after sorting the lines, when I used uniq -c, there was only one line that occurred only once.

<img width="314" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/98597891-930b-4df5-9e42-d1a96e9cbcac">

This was the password.
There were quite a few things to be learned in this level like uniq, sort , piping and redirection.
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Level 9

This one said human readable. So I thought, I've already done this. Then I realised this one had human readable strings and not files. Though I new it would be useless, I saw the contents of data.txt. All gibberish as expected.

So I saw the 'commands you may need' and saw strings. I checked the man page for strings. It said shows the printable files, seemed good enough. So I tried it. 

<img width="254" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/06f23cfd-f62b-41ea-b2d8-a5338cac9072">

On scrolling through the output, I saw a few lines with multiple '=' signs but that wasn't an efficient way to find the password.
Now how many does several mean? I thought 4 seems reasonable.
So I just used strings and piped it into grep with 4 equal to signs.

<img width="364" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/a3f37e39-6348-4990-84f8-232177280e06">

That did it. Got the password. This one was easier than I anticipated.
So this level taught me about the strings command.

G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Level 10 

The next password was in data.txt but encoded in base64. I looked up the man page for base64 and it said it encodes or decodes data. I read a bit about it. I learned that it uses a base64 specific coding format to encode binary strings to text and vice versa.
The man page said -d is used for decoding.

So first i just printed the contents of data.txt to have a look and then used base64 with -d. It worked on the first time. I didn't even look up any examples for this one. This level was pretty quick to finish. 

<img width="556" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/e608ae0d-4d00-4ed0-b11c-47968517fe76">

Something new to learn in every level though.

6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Level 11

The next file had the text rotated by 13. Didn't make much sense initially so I looked up the linked wikipedia page.
It's pretty straightforward. Just replacing the alphabets by the 13th alphabet after it. Then there was even an example on the wikipedia page for using tr for rot13 in unix. Nevertheless I looked up the man page for tr, but wikipedia explained it pretty well. The example in wikipedia had used text directly , while I had to use data.txt. The syntax for tr didn't have anything argument after the encoding key thing but I tried it anyways. 

When that didn't work I used cat and piped the tr command. That was it. It worked.

<img width="447" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/2739d4fd-56f1-4c23-879d-20f64660aedb">

Even this one didn't take as much time as the few middle levels.


It was a fun and informative experience doing these 11 levels. It doesn't seem like much because I did these over a span of 4 days but when I looked through all the things I learned over the levels, it sums up to some significance. It was a great experience overall.

## Level 12

This level was something else. I haven't spent so much time on any level before this one. I had to go through like 6 or 7 man pages to fully understand the stuff here.

First of all I looked up the wikipedia page on hexdump and it's basically the hexadecimal form of any data but in a specific format.
The question had some guidelines so first I checked the man page for mkdir which was pretty easy to understand.
I made the directory , then copied the file into the directory after checking the man page for cp.
Then I saw the xxd command and learned that xxd -r reverses the hex dump to its original text. Well it didn't work initially. I found that the reversed text had to be stored in another file. I thought that was it, that I'd now see the reversed text. I forgot about the repeatedly compressed part.

Then I checked the file type and read the man pages for gzip and bzip2 which was pretty straightforward too.
After this I tried to extract the files from the gzip. 

<img width="947" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/5fd0b9fb-eb2f-43f6-98ca-197e84487481">

It clearly did nothing. It took me a very long time to figure out about the file extensions and that I would have to change the file extension using mv every time. Eventually, it worked. Well I didn't realise it worked until I saw the file type.

<img width="950" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/38e2a338-7508-4e3b-b8dc-f07bc93e8405">

Then the file was in bzip2 format then gzip again and then it said posix tar archive. 

<img width="946" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/fca4b790-7532-4e25-b2d8-6ad7d5d7c75d">

So now I looked up the man page for tar. I learned that it is used to create and extract archive files. I saw a few examples for it. A google search told me that tar -xf is used to extract tar files. 

<img width="443" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/1bcfe1a2-ffd8-4838-b906-664e2a6f3a37">

I used the tar command. I realised that the data was no longer in the info file. I mean in gzip and bzip2, the same file was being decompressed. Over here, the data from info was extracted to another file. 
Then I got a hang of it and had to do the decompressing and extracting a few times before I got some ascii text.

<img width="941" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/c6bd7b04-291b-41f2-b940-d368b3f775d2">

Got the password finally.
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Level 13
For this level, first I read the helpful reading material. It was really informative and hade some interesting things, but I didn't see anything that I could apply for this level.
Then I read through every man page mentioned, still didn'y get any sense of direction as to what I should do. When a few google searches didn't help, I had to turn to youtube for help.

I learned that I had to use ssh -i along with @localhost.
This didn't work though. I though there was something wrong with the configuration in my wsl. I spent a lot of time thinking localhost wasn't working on my machine. After some help, I realised that I was missing -p. I felt really stupid as I had spent a considerable amount of time looking at a completely different thing.

Anyways, now I was logged in as bandit14, and I got the password.
<img width="617" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/381f1014-2851-4730-8afa-0018944e597c">

## Level 14

This level requres us to enter a password into port 30000. I saw that video which explains how the internet works, and I read about ip addresses. Then I read the man page for netcat. nc would do the job for this level. I also learned that unlike ssh nc doesn't require -p for the port. The syntax directly requires the port.

<img width="365" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/6bf8508c-f998-454d-850c-590c7733038f">

This required two tries as I didn't realise the password was being read.

## Level 15

For this level, similar stuff had to be done but while using ssl encryption. I checked the man page for openssl and s_client. Didn't quite get what to do so I googled what to use for encrypting using ssl. There was this man page for s_client which had connect and the host and port name.
Initially, I tried using s_client independently, I then learned that it is to be preceded by openssl.

<img width="502" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/04f36441-24e9-4357-9f73-66c61134abb0">

It gave a lot of stuff and there was read r block in that. So I read the connected commands thing and I don't know if I fully understood, but it said that without using -ign_eof it gives all the data raceived from the server. 

So now I tried it with the -ign_eof. It still gave all that stuff. It didn't matter if I used -ign_eof or not, upon entering the password at the end, I got the next password. 
Oh and just an observation, that unlike ssh the passwords are visible in this.

<img width="389" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/eb76938b-2cee-494b-9f92-136f94cc8558">

## Level 16

This level required scanning of the ports. I looked up the man page for nmap, finding the port ranges thing was easy enough but I couldn't see anything that would give me details about ssl. I googled it and there was this -sV which would scan for ssl too. I tried it but it took too long, so I just ended the command. It still gave an output. So 2 of the ports had ssl written beside them. -sV narrowed it down to 2 ports. Now I could just check both of them.

<img width="950" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/ee1ef862-e678-4cd2-a87d-56772832b314">

I found the right one, but it didn't give the password. It gave an rsa key.

<img width="483" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/20615de0-a050-4dd7-8c65-521d6a2ab9f4">

Now though I knew there was a very slim chance it would work, I just pasted the key next to ssh and tried to login. Of course it didn't work. I googled how to use an rsa key, I would have to store it in a file and change the permissions for that file too. This required the use of a text editor, and I saw vim at one or teo places. So I used that.

<img width="596" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/9932afb7-10df-4730-82b0-ec3bfb891900">

I saved a file on my device with the rsa key and used it for logging in. It took 2 tries to save the file correctly using vim. Honestly, I had no idea how to use it, I was just following the steps. I was able to do it myself the second time though.

## Level 17
This one was easier than the previous few. Dealing with normal files again. Anyways, I looked up the man page for diff, and it was used to compare files line by line. There were a bunch of arguments for diff, but simply using it without any arguments also gave the desired output. 

<img width="437" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/aad42128-48dc-4173-a9ac-e38cce693893">

Then when I logged in using the password, it worked but I was logged out again. That was supposed to happen. I saw the byebye thing in the note.

## Level 18

In this level I am unable to login to bandit18 because the .bashrc file is modified to do so. This was stated in the question. 

I googled this, and as per my crude understanding, as sson as ssh is used, there is a .bashrc file generated which is logging me out. To get around this, the -t argument can be used with ssh as it won't give a persistent connection, but will rather allow me to execute a command directly in the ssh statement itself, so no constant connection required. Before logging me out, the command will have run. 
This was my perception of what is happening, I may be inaccurate.

Anyways, that did it. Got the password

<img width="632" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/75b45e40-08ca-4803-b5ae-5a24414e275b">

Now this worked because I knew the file was in readme. I wouldn't be able to get the password if I didn't know the file name.

I saw an alternative on a website, which used /bin/sh after the normal ssh command with -t. I tried it and it allowed me to login without and maintain the connection. 

I have absolutely no idea how this works and what /bin/sh is. Apparently it forces the login. 

<img width="612" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/47ebfdf6-6489-4354-8c0e-9347ac639318">

## Level 19 
