## Table of Contents
- [About vsCodeSnippets](#About%20vsCodeSnippets)
- [How to Download](#How%20to%20Download)
	- [Download using PowerShell CLI via git clone in](#Download%20using%20PowerShell%20CLI%20via%20git%20clone%20in)
	- [Download using ZIP](#Download%20using%20ZIP)
		- [Cant find the directory?](#Download%20using%20ZIP#Cant%20find%20the%20directory?)
- [Dependencies](#Dependencies)
	- [Cplusplus Snippets](#Cant%20find%20the%20directory?#Cplusplus%20Snippets)
	- [Cisco Snippets](#Cant%20find%20the%20directory?#Cisco%20Snippets)
		- [Install](#Download%20using%20ZIP#Install)
- [Want to make changes and customize your snippets?](#Want%20to%20make%20changes%20and%20customize%20your%20snippets?)
	- [Changing the name used to paste snippet](#Want%20to%20make%20changes%20and%20customize%20your%20snippets?#Changing%20the%20name%20used%20to%20paste%20snippet)
	- [Changing the configs in the body of the snippet](#Want%20to%20make%20changes%20and%20customize%20your%20snippets?#Changing%20the%20configs%20in%20the%20body%20of%20the%20snippet)
- [How to use the snippets](#How%20to%20use%20the%20snippets)
	- [Cisco.json prefix Structure](#Install#Cisco.json%20prefix%20Structure)

## About vsCodeSnippets
- Code Snippets for vsCode. 
	- Allows the user to autofill common code sections with a short abbreviation.
	- These abbreviation are configurable to your liking. Click [Here](#Want%20to%20make%20changes%20and%20customize%20your%20snippets?) to see how.

## How to Download 
- Here you will find various method of download. 
- The CLI method is best to be able stay up to date with any improvements using `git pull`. Using the ZIP method you will have to follow the steps found here each time you wish to update the Code Snippet Files.

### Download using PowerShell CLI via git clone in 
- Copy and paste the code below to navigate to the location where vsCode stores User Code Snippets. don't forget to change the area that reads  ***\<CHANGE THIS TO YOUR USER NAME>*** to your user name. 

```
cd C:\Users\<CHANGE THIS TO YOUR USER NAME>\AppData\Roaming\Code\User\snippets
```

- If you cant find this file location go to [Cant find the directory?](#Download using ZIP#Cant%20find%20the%20directory?)

- NOTE: If you already have configurations inside this directory you may want to run the following command inside another directory and  `mv` or `cp`  only the files you wish to add to your existing configuration to not cause duplicate name collisions or linking errors.

- Inside `/your/path/to/Code/User/snippets` run the following command to add the twoThreeFiveEight/vsCodeSnippets repo files to this directory. 
	

```
git clone https://github.com/twoThreeFiveEight/vsCodeSnippets.git
```

- Once the repo exists inside your directory you will be able to use the snippets found inside the JSON files.

### Download using ZIP
- Click on ***<>Code*** drop down box on the [main repo page](https://github.com/twoThreeFiveEight/vsCodeSnippets) 
- open ***File Explorer***
- Go to your ***Downloads*** directory
- Download the ZIP file.
- unzip this file inside your ***Download*** directory. 
- Click the unzipped directory and copy all the files inside the directory.
- Navigate to the location `C:\Users\<CHANGE THIS TO YOUR USER NAME>\AppData\Roaming\Code\User\snippets` making sure to change the area that reads  ***\<CHANGE THIS TO YOUR USER NAME>*** to your user name. 
- NOTE: If you already have configurations inside this directory you may want to run the following command inside another directory and  `mv` or `cp`  only the files you wish to add to your existing configuration to not cause duplicate name collisions or linking errors.
- Paste all the files into this directory.
- You will now be able to use the snippets.


#### Cant find the directory?
- Open ***vsCode***
- Navigate to ***File*** then ***Preferences***
- Click on ***Configure User Snippets***

![snippets location](/resources/figure0-1.png)
(Figure (0-1)

- When the ***Snippets File*** search bar opens click on cisco.json file
- If cisco.json is not an option go to 

![Snippet Config drop down menu](/resources/figure0-2.png)
Figure (0-2)

- When the file opens find the file path at the top of the editor.  Figure 0-3 and figure 0-4 shows the where you can find the path.

![path image](/resources/figure0-3.png)
figure (0-3)
![closer look at path image](/resources/figure0-4.png)
figure (0-4)

- Open CLI and Navigate to the file path you found in the previous steps. 
	- If you are using WSL like me you the file path will look like this
![look at wsl path](/resources/WSLpathlook.png)

- Inside `/your/path/to/Code/User/snippets` run the following command to add the vsCodeSnippets repo files to this directory. 
	- NOTE: If you already have configurations inside this directory you may want to run the following command inside another directory and  `mv` or `cp`  only the files you wish to add to your existing configuration. 

```
git clone https://github.com/twoThreeFiveEight/vsCodeSnippets.git
```

- Once the repo exists inside your directory you will be able to use the snippets found inside the JSON files.

## Dependencies 
##### Cplusplus Snippets
- You will need to have some LSP like clangd to create a cpp.json file. 
- I am using C/C++ by Microsoft
![c/c++ dependency](/resources/figure1-1.png)
Figure (1-1)

##### Cisco Snippets
- You will need the Cisco IOS Syntax extension in vsCode to be able to add a json file containing the cisco configurations found inside this repo.
- I am using the Cisco IOS Syntax extension by jamiewoodio
![cisco IOS dependency](/resources/figure1-2.png)
Figure (1-2)


#### Install 
- In vsCode navigate to ***Extensions*** found inside the left option bar. 
- Search for the extensions mentioned above. Click install.


## Want to make changes and customize your snippets?

- You will need to already have the repo installed for this example and have an understand on how to use it before making changes.

### Changing the name used to paste snippet
- Open ***vsCode***
- Navigate to ***File*** then ***Preferences***
- Click on ***Configure User Snippets***

![Figure0-1](/resources/figure0-1.png)
Figure (2-1)

- When the ***Snippets File*** search bar opens click on the language you wish to add the configurations to.
- in our example we will use the cisco.json file

![snippets menu](/resources/figure0-2.png)
Figure (2-2)

- We will only go over how to change the snippet code and not talk about what the JSON is doing.

- The `    "prefix": "cInitial",    ` field below sets our abbreviation name. We can change this to any name we would rather use to have this snippet paste its self into our configurations (program).

```
    "Cisco Initial Configuration": {
        "prefix": "cInitial",
        "scope": "cisco",
        "body": [
            "hostname <name you want>",
            "enable secret <PASSWORD>",
            "username <USERNAME> secret <PASSWORD>",
            "line con 0",
            "logging synchronous",
            "login local",
            "line vty 0 4",
            "logging synchronous",
            "login local"
        ],

        "description": "Cisco Initial Configuration"

    },
```

-  As it stands currently we will need to start typing `cInitial` to allow the  us to select this snippet. example in figure 

![snippet use](/resources/figure2-3.png)
Figure (2-3)

- We will change this to `cMyCustomPreFix` to make this the new snippet command

```
    "Cisco Initial Configuration": {
        "prefix": "cMyCustomPreFix",     <----- WE CHANGED THIS HERE
        "scope": "cisco",
        "body": [
            "hostname <name you want>",
            "enable secret <PASSWORD>",
            "username <USERNAME> secret <PASSWORD>",
            "line con 0",
            "logging synchronous",
            "login local",
            "line vty 0 4",
            "logging synchronous",
            "login local"
        ],

        "description": "Cisco Initial Configuration"

    },
```

- Here is an example of what changes.

![customPrefixExample](/resources/figure2-4.png)
Figure (2-4)

### Changing the configs in the body of the snippet
- Very simple we just change, add, or delete the code inside the quotes found inside the ***body*** section of the json configuration

```
    "Cisco Initial Configuration": {
        "prefix": "cMyCustomPreFix",     
        "scope": "cisco",
        "body": [
            "hostname <name you want>",    <----- CHANGE THE CODE INSIDE THE QUOTES HERE
            "enable secret <PASSWORD>",    <----- OR HERE
            "username <USERNAME> secret <PASSWORD>", <----- OR HERE
            "line con 0",                            <----- OR HERE
            "logging synchronous",                   <----- OR HERE
            "login local",                           <----- OR HERE
            "line vty 0 4",                          <----- MAYBE YOU WISH TO DELETE THIS
            "logging synchronous",                   <----- OR THIS
            "login local"
        ],

        "description": "Cisco Initial Configuration"

    },
```

- Just be sure to verify your code prints correct afterward

## How to use the snippets

###### The file extension must be the correct language for the snippets you wish to use unless you created a ***Global User Snippet File***.  In the Figure (3-1) the name of the File is R1.ios the ***.ios*** has to be set to use the ***cisco.json*** snippets from the repo.


##### Cisco.json prefix Structure 
- Here we are using the ***cisco.ios*** snippets. 
	- Every snippet ***prefix*** was prefixed with the character  "c" to allow every snippet to populate inside the snippet menu box. 
		- After the character "c" the snippets will be under the category for which the snippets purpose falls under. So far there are 3 main categories
			- p == protocol (bgp, ospf, eigrp, ipsec, acl, rpvst+)
			- l2 == Layer 2 snippets (switchport, Access/trunk)
			- l3 == Layer 3 snippets (Layer 3 port-channels, layer 3 SVIs)
	
- If you do not know the snippets prefix simply type "c" then use ***DOWN ARROW*** to search for the snippet. 

![Look up example](/resources/figure3-1.png)
Figure (3-1)

| First Character | Second Character | following       |
| --------------- | ---------------- | --------------- |
| c               |    l2, l3, p, or name       | Name of snippet |

- That is basically how to use it. Play around and if you find a better solution to the structure feel free to submit a ***pull request*** to the repo explaining what you improved and why. 