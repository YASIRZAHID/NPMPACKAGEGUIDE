## GUIDE TO CREATING NPM PACKAGE 

this guide is for making a calculator package and relevant packages are installed 
this is a step by step guide for setting the right environment for the project 

##1 check if right environment is installed

    open command prompt type 
    ##a
        node -v

        command prompt should return the version you have intalled e.g

            v18.13.0     (your version might be diffrent)

    ##b
        tsc -v

        command prompt should return the version you have intalled e.g

            Version 4.8.4     (your version might be diffrent)

    ##c
        make sure that you have visual studio installed       

    (if any of above is not installed install it installation guide at end of document appendix d)    

##2 making a directory for our project

    now if you know how to make a new directory using command prompt do it(more detail at end of document appendix a)
                                    or
    create a new folder and open it 
    click in address bar 
    type cmd and press enter

##3 setting up typescript configuration file

    in command prompt type
    
    ##a
        tsc --init             (and press enter)

        this should create a tsconfig.json file in your directory

        make following changes in this file (more about selecting right values in end of document appendix b)
           
            change following values from whatever they are to following

        ##a1
                "target" to "ES2022" (or latest available) 
                
                it should look like this now
                    "target": "ES2022", 

        ##a2
                "module" to "NodeNext", 

                it should look like this now
                "module": "NodeNext", 

        #a3        
                "moduleResolution" to "NodeNext",

                it should look like this now
                "moduleResolution": "NodeNext",

        ##a4        
                "outDir" to "./bin",

                it should look like this now
                "outDir": "./bin",
        (do not forget to save when you are done making changes (ctrl + s))  
        

    ##b 
        npm init -y

        this should create a package.json file in your directory

        ALERT!! make sure the "name" in this directory is unique (appendix c at end of document) 

        make following changes in this file

        ##b1    

            in line 6 below "main": "index.js", enter 
                "type": "module", (in package.json file created in current directory)

            this should look like this now
                "main": "index.js",
                "type": "module", 
        ##b2    

            in line 7 below "type": "module", enter 
                "bin": {
                        "yasir_project00_calculator": "bin/index.js"
                 },

            this should look like this now (line 6 and 7)
                "type": "module",
                "bin": {
                    "yasir_project00_calculator": "bin/index.js"
                },
                   

 ##4 installing required NPM packages

    in command prompt type(each step is installing a package)

    ##a
        npm i inquirer

        this will install inquirer.js

    ##b 
        npm i chalk

        this will install chalk.js

    ##c 
        npm i chalk-animation

        this will install chalk-animator.js

    (each step will install package and also add relevant package to package.json file in dependencies) 

##5 adding installed package in node_modules types 

    in command prompt type

    ##a

        npm i @types/node -D

        this will add a folder node_modules (folder) and package-lock.json file to your current directory

    ##b

        npm i @types/chalk -D

    ##c

        npm i @types/chalk-animation -D

    ##d

        npm i @types/node -D   
    
    (each of these step will add respective package to node_modules @types folder as well as devdependencies in
    package.json file )

##6 create a file named .gitignore in main directory

    in this file type

    node_modules 

    this will prevent uploading node_modules when pushing to github

##7  create an index.ts file in main directory

    (just to test)

    type following code in this file

    console.log("hi")


    enter following command in terminal or command prompt

    tsc

    this should create a index.js file.

##8  write your code for whatever you are creating using typescript simply

    line one of your document must iclude following code (shebang #!)

        #! /usr/bin/env node

##9  compile/transpile your files in this case in terminal just type 
        
        tsc

##10 publishing to npm

   ##a create an npm account here

        "https://www.npmjs.com/signup"

    ##b in terminal/command prompt opened in current directory type

        npm login

        this will ask for your details or redirect you to the browser  for login

    ##c in terminal enter following command

        npm publish 

        this will publish your package

    ##d running your package 

        ##d1 make a new directory/folder 
            
            open command prompt(in this directory)

            type following command 

            npm i your_package_name    

            (this is name you have set in package .json directory)

            this step will install your package

        ##d2 run the package

            in command prompt enter following command

            npx your_package_name

            this will run your package    


## appendix a

    (press tab to get available paths (when applicable))
    cd      to change directory
    mkdir   to make directory
    ..      to move one level up in directory
    ./      directory starting in current folder

## appendix b 

    after uncommenting any attribute place cursor in value of any attribute

    press ctrl + SPACEBAR to see list of valid values

## appendix c

    npm search (CAN BE USED TO CHACK IF THE NAME YOU ARE USING IS AVAILABLE)

## appendix d 

    GUIDE TO INSTALL VISUAL STUDIO CODE

    "https://code.visualstudio.com/docs/setup/windows"




other usefull commands

npm i (CAN USE THIS COMMAND TO INSTALL dependencies LOCALLY PRESENT IN package.json)
