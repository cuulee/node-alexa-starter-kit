# Simple Amazon Alexa Starter Kit

This starter kit allows you to add new skills for Amazon Alexa easily. <br>
Configuration for <a href="https://developer.amazon.com/alexa">Amazon</a>
is generated automatically and saved to **amazonConfig.txt** file,
so all you have to do is to copy it to <a href="https://developer.amazon.com/alexa">Amazon Alexa website</a>

## Initialization
- ```git clone git@github.com:AlexSapoznikov/alexa-express-starter-kit.git```
- ```cd alexa-express-starter-kit/```
- ```npm install```

## Commands
- ```npm start``` - builds and starts server
- ```npm run start-dev``` - starts and restarts server on code change
- ```npm run build``` - builds without starting server
- ```npm run create-skill [-- --name=anyname]``` - creates new sample skill file in *skills* folder
- ```npm run expose``` - exposes your localhost to the internet
- ```npm run eslint``` - lints the code for errors

## The Structure

- Development is being done in *./src* folder.
- The builded code is generated to *./public* folder.
- Configuration files are located in *./config*.
- Skills are located in *./src/skills/* folder.
- Skills are included in *./src/skills.js* file.
- Server creates intents (endpoints) automatically using merged skills in *./src/skills.js* file.
- Scripts for generating amazon configuration and new skill files are located in *./src/scripts* folder.

## How to add new skills

- Add new skill file via terminal
```
npm run create-skill -- --name=myNewSkill
```
- Edit the skill file (*./src/skills/myNewSkill.js*).
- Start the server
```
    npm run start
    // or
    npm run start-dev
```

- For development, expose your localhost to the internet.
    - Start ngrok
    ```
        npm run expose
    ```
    - Look for the output to find alexa endpoint, it looks something like this: https://1234ccb1.ngrok.io/alexa

- Do a setup in <a href="https://developer.amazon.com/alexa">Amazon Alexa website</a>
    - Sign in to <a href="https://developer.amazon.com/alexa">Amazon Alexa website</a>
    - Add new skill
    - Copy-paste generated configuration from **./amazonConfig.txt** to required fields.
    - Use https url generated by ngrok in previous step
    
Alexa is now ready for testing.
- Use the command: *Alexa, ask [invocationName] [question using utterances]

## Licence

Copyright (c) 2017 Aleksandr Sapožnikov, NodeSWAT

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
