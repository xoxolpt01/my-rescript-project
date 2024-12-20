# Creating ReScript enviroment
## Installing Node.js

The first step is installing Node.js from official web-site:
    https://nodejs.org/en

Be sure that installed npm 
Because ReScript depends on Node.js for dependency management via npm
    (I personal use WSL based on Ubuntu)

```sh
  • sudo apt update
  • sudo apt install nodejs
```

Check versions:
```SH
  •  node -v  
  •  npm -v
```


## Initializing a new ReScript project
### Create new project folder
```SH
  •  mkdir "any project's name"
  •  cd "name"
```

### Initialize npm project
```SH
  •  npm init -y
```
The npm init -y command is used to quickly create a package.json file in 
the current directory without having to go through the interactive setup process. 
It automatically populates the package.json file with default values.


### Install ReScript
```SH
  •  npm install rescript
```

## Setup 
### Setup bsconfig.json with such contents:
```SH
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
```

### Create src folder 
```sh
  •  mkdir src
```
## Code writing and compiling 
### Create src/Example.res file

Put code there:
```sh
    let message = "Hello, ReScript!"
    Js.log(message)
```    
    
### Compile project
```sh
  •  npx rescript build
```
    It`s creating src/Example.bs.js file that's contains JavaScript-code

### Launch compiled JS code via Node.js
```sh
  •  node src/Example.bs.js
```

# In addition I`d like share with basic ReScript commands

### Compiling the project
```sh
  •  npx rescript build
```

### Run compilation in watch mode
```sh
  •  npx rescript build -w
```

### Cleaning up compilation results
```sh
  •  npx rescript clean
```

### Initializing a new ReScript project (template)
```sh
  •  npx rescript init
```


# Libraries installing 

If you want to use third-party libraries in ReScript, install them via npm and add them to bs-dependencies in bsconfig.json.
For example: 
```sh
  •  npm install @rescript/react
```
Into:
    "bs-dependencies": ["@rescript/react"]

### And now It`s ready to work ☺️
