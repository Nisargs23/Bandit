# Writeups
## Level 0
I started with overthewire bandit feeling a little clueless but it got easier to understand pretty soon
Level 0 was useful to understand the usage of the ssh command which provides communication over a network.
<img width="578" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/6a16ca6a-245b-4491-8023-4ba8db48af9a">

Level 0 was pretty straightforward as you had already shown us the basics.

<img width="257" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/767b04a7-7933-47d8-a4e2-dc6a170ff98b">

Then I used the ls and cat commands to access the file and read it.
## Level 1
The next task was to open a file called -. Of course I tried to simply open the file using cat but it didn'y work.Nothing happened infact. It didn't even give an error or anything.
It wasn't too difficult to solve though. A simple google search and the links provided on the level 1 page offered the solution.
I learned that the - character is used before entering commands and hence a command is expected further. To get around this issue we need to use ./ before the filename.

<img width="267" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/13e66453-1f17-49cd-a174-deb9690a1a16">

## Level 2
Using the password in level 1 i went on to the next level. There was a file called spaces in this filename.
I went through few of the man pages and read about the cd command. And as the question specifically mentioned home directory, I tried to use the cd command. That didn't work though. I went through the helpful reading material thing and it gave the solution. 
Though I think I should have guessed the issue by looking at the filename.
Anyways the spaces were the issue and I found that it was treating all the words as different names instead of a whole filename. I culd access the file by putting the filename in double quotes. Another thing that can be done is using the \ before each character.

<img width="386" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/905510a9-9663-4c2b-a8f0-58b0b73eff2e">

## Level 3
Now i logged in again and used ls to see inhere written in blue. As the question said inhere directory I assumed it was a directory and used the cd command. This got me into the directory. Then I used ls again but there was no result.
Now as the question said hidden file, I made a google search on how to see hidden files in a directory. The first result said that to see the hidden files we can use -a after the ls command. 
This enables all the files to be seen. 
It worked and i saw the .hidden file. It was accessible by using cat.
So in this level i learved to access a directory and also see files that are hidden. 
I also googled how to exit an entered directory incase i needed to go back out. I found I can simply use cd.

<img width="295" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/78418825-61c8-4d0d-9948-534a61b611f1">

## Level 4
This level took me quite some time.
I logged in and did the usual stuff. ls and cd command to get into the directory. There were a bunch of files and i tried opening one of them.
It had gibberish in it. Well at least gibberish to me. So i guess that's what human unreadable means.
I used the man page for file as it said that file command can determine the file type.
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


Now the problem was that the parameters I was setting seemed to work but that wasn't narrowing down anything. It was only when I saw one of the examples on the man page that I realised that all of them work together. In hindsight that made sense as you would need to set different parameters to find a file.Anyways it worked after a while.

<img width="491" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/9c84295c-f2fa-4eb8-992f-399589d03cc2">

P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Level 6
Some new parameters and the size one is already known. It was easy enough to finf=d the user and group commands on the man page for find. They had pretty simple syntaxes.

Honestly, I thought "that was pretty quick". Until I used the command. No result. Oh yeah, I didn't change the directory.
So ls. Only this time no directory. ls -a . Still no directory, but some names which made no sense and gave a bunch of gibberish on trying to access it. 
So I read the question again, and it said the whole server.
On searching on google, I learned that for a specific directory, you can just use find /directory instead of shifting to the directory first. This was of no use for this particular level though as the file wasn't in any diretory. And simply specifying the canditions without any directory didn't seem to work. So something was missing

It had to be find / instead of just find.

<img width="624" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/76bd9fdf-1eec-4467-9819-27040a4782d7">

Well it worked. Kind of. There were a whole bunch of permission denied. One of the files stood out on closer inspection but that didn't seem like a very efficient way to find the file. So I googled the question. It led me to a command 2>/dev/null.
This made absolutely no sense. So I tried to find something else that I might unserstand but I found only this to hide the denied permissions. 
So I tried it and sure enough, the correct file was the only one displayed.

<img width="544" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/4025ad5c-d2e9-4f7b-9d21-23af39f7aef6">

z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
## Level 7

For this level there was a file name and the word next to it.
on using ls, there was only one file, data.txt.
When I tried to see the contents, it just kept going. So obviusly, I had to find the word millionth from data.txt

<img width="242" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/71d16723-ab84-45be-8a58-16902a54eb82">

I quickly went through the man page for grep. I looked for examples, but there was only one which was a little complicated for me. So I just googled the syntax for basic grep command. Et voila, there was the word and the password next to it.
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

This was the password
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Level 9

This one said human readable. So I thought, I've already done this. Then I realised this one had human readble strings and not files. Though I new it would be useless, I saw the contents of data.txt. All gibberish as expected.

So I saw the 'commands you may need' and saw strings. I checked the man page for strings. It said shows the printable files, seemed good enough. So I tried it. 

<img width="254" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/06f23cfd-f62b-41ea-b2d8-a5338cac9072">

On scrolling through the output, I saw a few lines with multiple '=' signs but that wasn't an efficient way to find the password.
Now how many does several mean? I thought 4 seems reasonable.
So I just used strings and piped it into grep with 4 equal to signs.

<img width="364" alt="image" src="https://github.com/Nisargs23/Bandit/assets/148000598/a3f37e39-6348-4990-84f8-232177280e06">

That did it. Got the password. This one was easier than I anticipated.
So this level taught me about the strings command.

G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
