## Execute It
# Realtime Code Collaboration and Code Execution Platform


> This Platform is Deployed at https://executeit.ml

> Presentation Link: https://github.com/AVC0706/Eduthon/blob/master/assets/Tres-Comas.pdf

> Youtube Video Link: https://youtu.be/xq-h6HmpOeE

We are planning to build a realtime code collaboration platform, which can be used as an educative aid while conducting online practical sessions.

![alt text](/assets/screencapture-executeit-ml-login-2020-09-06-04_35_18.png "Login Screen")

![alt text](/assets/screencapture-executeit-ml-rooms-2020-09-06-07_40_39.png "Rooms Screen")

![alt text](/assets/Screenshot_20200906_095424.png "Workspace Screen")


### What lead us to develop this platform ?

This pandemic has hit us hard, but with time everything is starting to come online so is the case with our colleges.

All lectures and CODING PRACTICALS are being conducted online, mostly through PPTs and screen sharing,
while this way is OK'ish for theory lectures but it becomes really hard to coupe up with online PRACTICALS.

### Some Caveats of the current way of online PRACTICAL sessions :
  * All the students do not have the same coding environment and some of them don't even have Linux installed. 
  * If the student wants to share code or even if teacher wants to share a code, they need to send file which then needs to be run locally, hence consuming more time.
  * Debugging and doubt solving in a code is really cumbersome and teacher cannot help student in realtime.
  * Poor network connection is the biggest hurdle of all due to which quality of share may be bad and code may not be visible clearly.
  
### What we propose ? 
  * On our platform teacher will create a room, will share invite link.
  * After the room is created a linux container will be created and all users will be able to access that linux environment.
  * Students will join the room, which will put them and the teacher in the same coding environment.
  * Now they can create files and start coding in realtime using our online code editor, including syntax highlighting and all other features.
  * Each file can be modified by multiple users at the same time, and changes will be reflected to all the users. ( Google Doc like but with an IDE )
  * A dedicated terminal will be accessible to each user inside the same linux container.
  * Students and Teachers will be able to communicate with each other through text and voice chat.
  * As all communications will happen through websocktes, therefore consuming less bandwidth than current online video sessions. 
  
![alt text](/assets/eduthon.png "Flow")
  
 ### Installation
  This project uses docker. So ensure that you have Docker and Docker Compose installed on your system For installation instructions refer: https://docs.docker.com/install/
Also, make sure that you have port `80` and `3000` open on the host
  
#### Building all docker files
 1. cd to`/user-image`directory and run `docker build . -t user-image` 
 2. cd to `/main-server` and run `docker-compose -f docker-compose.dev.yml build app`
 
#### Creating a bridge network
 1. Before starting servers, create a bridge network `docker network create -d bridge executeit`

#### Start the Servers
 1. cd to `/main-server` and run `docker-compose -f docker-compose.dev.yml up`. This will start traefik, convergence, mongo-db, and main-server
 2. Traefik will serve as reverse proxy to all the container through `http://localhost`

#### Start the React Client
 1. cd to `/main-client` and run `npm install`
 2. Then start the server by `npm start`. Please make sure that the client is hosted on port 3000 only because the port is added on google cloud console.
 
 Now navigate to `http://localhost:3000` and start exploring our project
 
 ### System Architecture

![alt text](/assets/System_Architecture.png "System Architecture")

## Contributors
* Pratik Daigavane [Github](https://github.com/pratikdaigavane) | [Linkedin](https://linkedin.com/in/pratikdaigavane) | [Portfolio](https://www.pratikdaigavane.me)

* Prathamesh Shiralkar [Github](https://github.com/pnshiralkar) | [Linkedin](https://linkedin.com/in/pnshiralkar) | [Portfolio](https://pratham.live)

* Atharv Chavan [Github](https://github.com/AVC0706) | [Linkedin](https://linkedin.com/in/AVC0706) | [Portfolio](https://www.atharvchavan.me)


 
