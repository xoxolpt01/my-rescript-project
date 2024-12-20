# Creating ReScript enviroment
## Installing Node.js

The first step is installing Node.js from official web-site:
    https://nodejs.org/en

Be sure that installed npm 
Because ReScript depends on Node.js for dependency management via npm
    (I personal use WSL based on Ubuntu)

   • `sudo apt update`
   • `sudo apt install nodejs`

Check versions:
  •  `node -v  `
  •  `npm -v   `


## Initializing a new ReScript project
### Create new project folder

  •  mkdir "any project`s name"
  •  cd "name"


### Initialize npm project

  •  npm init -y

The npm init -y command is used to quickly create a package.json file in 
the current directory without having to go through the interactive setup process. 
It automatically populates the package.json file with default values.


### Install ReScript

  •  npm install rescript


## Setup 
### Setup bsconfig.json with such contents:

{
  "name": "my-rescript-project",
  "sources": [
    {
      "dir": "src",
      "subdirs": true
    }
  ],
  "package-specs": {
    "module": "commonjs",
    "in-source": true
  },
  "suffix": ".bs.js",
  "bs-dependencies": []
}


### Create src folder 

  •  mkdir src

## Code writing and compiling 
### Create src/Example.res file

Put code there:

    let message = "Hello, ReScript!"
    Js.log(message)
    
    
### Compile project

  `•  npx rescript build`

    It`s creating src/Example.bs.js file that's contains JavaScript-code

### Launch compiled JS code via Node.js

  •  node src/Example.bs.js


# In addition I`d like share with basic ReScript commands

### Compiling the project

  •  npx rescript build


### Run compilation in watch mode

  •  npx rescript build -w


### Cleaning up compilation results

  •  npx rescript clean


### Initializing a new ReScript project (template)

  •  npx rescript init



# Libraries installing 

If you want to use third-party libraries in ReScript, install them via npm and add them to bs-dependencies in bsconfig.json.
For example: 

  •  npm install @rescript/react

Into:
    "bs-dependencies": ["@rescript/react"]
