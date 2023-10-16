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
