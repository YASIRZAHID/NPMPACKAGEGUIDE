# GUIDE TO CREATING NPM PACKAGE #

This guide is for making a calculator package and relevant packages are installed, 
This is a step by step guide for setting the right environment for the project 

## 1 Check if right environment is installed ##

Open command prompt and type 
   ### Check if node is installed
    
        node -v
        
Command prompt should return the version you have intalled e.g

            v18.13.0     (your version might be diffrent)

   ### Check if typescript is installed
        tsc -v

Command prompt should return the version you have intalled e.g

         Version 4.8.4     (your version might be diffrent)

   ### Make sure visual studio is installed
Make sure that you have visual studio installed       

(if any of above is not installed install it installation guide at end of document appendix d)    

## 2 Making a directory for our project

Now if you know how to make a new directory using command prompt do it(more detail at end of document appendix a)
or
Create a new folder and open it 
Click in address bar 
Type cmd and press enter

## 3 Setting up typescript configuration file

In command prompt type
    
   ### Create and edit tsconfig.json file
        tsc --init             (and press enter)

This should create a tsconfig.json file in your directory

Take following changes in this file (more about selecting right values in end of document appendix b)
           
Change following values from whatever they are to following

   #### Set target to latest ecmascript
                "target" to "ES2022" (or latest available) 
It should look like this now

                "target": "ES2022", 

   #### Set module to Nodenext
                "module" to "NodeNext", 
It should look like this now

                "module": "NodeNext", 

   #### Set resolution to Nodenext        
                "moduleResolution" to "NodeNext",
It should look like this now

                "moduleResolution": "NodeNext",

   #### Set outDir to Nodenext
                "outDir" to "./bin",
It should look like this now

                "outDir": "./bin",
                
(do not forget to save when you are done making changes (ctrl + s))  
        

   ### Create and edit package.json file
        npm init -y
(type in command prompt)        

This should create a package.json file in your directory
ALERT!! make sure the "name" in this directory is unique (appendix c at end of document) 
Make following changes in this file

   #### Setting type to module    
In line 6 below "main": "index.js", enter 

                "type": "module", (in package.json file created in current directory)
                
This should look like this now

                "main": "index.js",
                "type": "module", 
                
   #### Setting bin directory    

In line 7 below "type": "module", enter 

                "bin": {
                        "yasir_project00_calculator": "bin/index.js"
                 },

This should look like this now (line 6 and 7)

                "type": "module",
                "bin": {
                    "yasir_project00_calculator": "bin/index.js"
                },
                   
Don,t forget to save (ctrl + s)
 ## 4 Installing required NPM packages

In command prompt type(each step is installing a package)

   ### Install inquirer
        npm i inquirer

This will install inquirer.js

   ### Install chalk
        npm i chalk

This will install chalk.js (used for beautifull text layout on cli)

   ### Install chalk-animation
        npm i chalk-animation

This will install chalk-animator.js
(each step will install package and also add relevant package to package.json file in dependencies) 

## 5 Adding installed package in node_modules types and devdependencies 

In command prompt type

   ### Adding node

        npm i @types/node -D

This will add a folder node_modules (folder) and package-lock.json file to your current directory

   ### Adding chalk

        npm i @types/chalk -D

   ### Adding chalk-animation

        npm i @types/chalk-animation -D

   ### Adding inquirer ###

        npm i @types/inquirer -D   
    
(each of these step will add respective package to node_modules @types folder as well as devdependencies in package.json file )

## 6 Create a file named .gitignore in main directory

In this file type

    node_modules 

This will prevent uploading node_modules when pushing to github

## 7  Create an index.ts file in main directory

(just to test)
Type following code in this file

    console.log("hi")


Enter following command in terminal or command prompt

    tsc

This should create a index.js file.

## 8  Write your code for whatever you are creating using typescript simply

Line one of your document must iclude following code (shebang #!)

        #! /usr/bin/env node

## 9  Compile/transpile your files in this case in terminal just type 
        
        tsc

## 10 Publishing to npm

   ### Create an npm account here

"https://www.npmjs.com/signup"

   ### Login to NPM
   
In terminal/command prompt opened in current directory type

        npm login

This will ask for your details or redirect you to the browser  for login

   ### Publishing package to NPM account
   
In terminal enter following command

        npm publish 

This will publish your package

   ### Running your package 

   #### Make a new directory/folder 
            
Open command prompt(in this directory)
Type following command 

            npm i your_package_name   
            
(this is name you have set in package .json directory)
This step will install your package

   #### Run the package

In command prompt enter following command

            npx your_package_name

This will run your package    


## Appendix a

(press tab to get available paths (when applicable))
    cd      to change directory
    mkdir   to make directory
    ..      to move one level up in directory
    ./      directory starting in current folder

## Appendix b 

After uncommenting any attribute place cursor in value of any attribute

    press ctrl + SPACEBAR to see list of valid values

## Appendix c

    npm search 
(CAN BE USED TO CHECK IF THE NAME YOU ARE USING IS AVAILABLE)

## Appendix d 

GUIDE TO INSTALL VISUAL STUDIO CODE

"https://code.visualstudio.com/docs/setup/windows"


Other usefull commands

   npm i 

(CAN USE THIS COMMAND TO INSTALL dependencies LOCALLY PRESENT IN package.json)

# My Project
Here,s the command to install the project I published using the above procedure

      npm i yasir_project00_calculator

Then run the package using this command

      npx yasir_project00_calculator
