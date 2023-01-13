# GUIDE TO CREATING NPM PACKAGE #

this guide is for making a calculator package and relevant packages are installed 
this is a step by step guide for setting the right environment for the project 

## 1 Check if right environment is installed ##

open command prompt and type 
   ### Check if node is installed
    
        node -v
        
        command prompt should return the version you have intalled e.g

            v18.13.0     (your version might be diffrent)

   ### Check if type script is installed
        tsc -v

        command prompt should return the version you have intalled e.g

            Version 4.8.4     (your version might be diffrent)

   ### Make sure visual studio is installed
        make sure that you have visual studio installed       

    (if any of above is not installed install it installation guide at end of document appendix d)    

## 2 Making a directory for our project

    now if you know how to make a new directory using command prompt do it(more detail at end of document appendix a)
                                    or
    create a new folder and open it 
    click in address bar 
    type cmd and press enter

## 3 Setting up typescript configuration file

    in command prompt type
    
   ### Create and edit tsconfig.json file
        tsc --init             (and press enter)

        this should create a tsconfig.json file in your directory

        make following changes in this file (more about selecting right values in end of document appendix b)
           
            change following values from whatever they are to following

   #### Set target to latest ecmascript
                "target" to "ES2022" (or latest available) 
                
                it should look like this now
                    "target": "ES2022", 

   #### Set module to Nodenext
                "module" to "NodeNext", 

                it should look like this now
                "module": "NodeNext", 

   #### Set resolution to Nodenext        
                "moduleResolution" to "NodeNext",

                it should look like this now
                "moduleResolution": "NodeNext",

   #### Set outDir to Nodenext
                "outDir" to "./bin",

                it should look like this now
                "outDir": "./bin",
        (do not forget to save when you are done making changes (ctrl + s))  
        

   ### Create aand edit package.json file
        npm init -y

        this should create a package.json file in your directory

        ALERT!! make sure the "name" in this directory is unique (appendix c at end of document) 

        make following changes in this file

   #### Setting type to module    

            in line 6 below "main": "index.js", enter 
                "type": "module", (in package.json file created in current directory)

            this should look like this now
                "main": "index.js",
                "type": "module", 
   #### Setting bin directory    

            in line 7 below "type": "module", enter 
                "bin": {
                        "yasir_project00_calculator": "bin/index.js"
                 },

            this should look like this now (line 6 and 7)
                "type": "module",
                "bin": {
                    "yasir_project00_calculator": "bin/index.js"
                },
                   

 ## 4 Installing required NPM packages

    in command prompt type(each step is installing a package)

   ### Install inquirer
        npm i inquirer

        this will install inquirer.js

   ### Install chalk
        npm i chalk

        this will install chalk.js (used for beautifull text layout on cli)

   ### Install chalk-animation
        npm i chalk-animation

        this will install chalk-animator.js

    (each step will install package and also add relevant package to package.json file in dependencies) 

## 5 Adding installed package in node_modules types and devdependencies 

    in command prompt type

   ### Adding node

        npm i @types/node -D

        this will add a folder node_modules (folder) and package-lock.json file to your current directory

   ### Adding chalk

        npm i @types/chalk -D

   ### adding chalk-animation

        npm i @types/chalk-animation -D

   ### Adding inquirer ###

        npm i @types/inquirer -D   
    
    (each of these step will add respective package to node_modules @types folder as well as devdependencies in
    package.json file )

## 6 Create a file named .gitignore in main directory

    in this file type

    node_modules 

    this will prevent uploading node_modules when pushing to github

## 7  Create an index.ts file in main directory

    (just to test)

    type following code in this file

    console.log("hi")


    enter following command in terminal or command prompt

    tsc

    this should create a index.js file.

## 8  Write your code for whatever you are creating using typescript simply

    line one of your document must iclude following code (shebang #!)

        #! /usr/bin/env node

## 9  Compile/transpile your files in this case in terminal just type 
        
        tsc

## 10 Publishing to npm

   ### Create an npm account here

        "https://www.npmjs.com/signup"

   ### Login to NPM
   
        In terminal/command prompt opened in current directory type

        npm login

        this will ask for your details or redirect you to the browser  for login

   ### Publishing package to NPM account
   
        in terminal enter following command

        npm publish 

        this will publish your package

   ### Running your package 

   #### Make a new directory/folder 
            
            open command prompt(in this directory)

            type following command 

            npm i your_package_name    

            (this is name you have set in package .json directory)

            this step will install your package

   #### Run the package

            in command prompt enter following command

            npx your_package_name

            this will run your package    


## Appendix a

    (press tab to get available paths (when applicable))
    cd      to change directory
    mkdir   to make directory
    ..      to move one level up in directory
    ./      directory starting in current folder

## Appendix b 

    after uncommenting any attribute place cursor in value of any attribute

    press ctrl + SPACEBAR to see list of valid values

## Appendix c

    npm search (CAN BE USED TO CHACK IF THE NAME YOU ARE USING IS AVAILABLE)

## Appendix d 

    GUIDE TO INSTALL VISUAL STUDIO CODE

    "https://code.visualstudio.com/docs/setup/windows"




other usefull commands

npm i (CAN USE THIS COMMAND TO INSTALL dependencies LOCALLY PRESENT IN package.json)
