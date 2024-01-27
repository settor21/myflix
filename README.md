# myflix
Project for DevOps and Microservices course @UoDundee

Design
DevOps Pipeline
https://ibb.co/VwGnSKp

Microservice Architecture
https://ibb.co/4Jx6jY5

Implementation
Contains 3 Flask microservices for 
- user authentication (https://github.com/settor21/myFlix_userAccess)
- subscriptions (https://github.com/settor21/myFlix_userSubscriptions)
- video streaming (https://github.com/settor21/myFlix_videoCatalogue)

Was deployed on Google Cloud VM instances running Ubuntu (20GB).
Jenkins was used to load the coad from Github and dockerize it in the remote server.

An VM instance running NGINX was setup to 
 - use the domain name myflix.world for https access and SSL certification.
 - Perform load balancing across multiple instances of the production server running the 3 dockerized microservices or the 2 dockerized DB services
 - 
Another VM instance was created to setup databases for use in the applications (MongoDB and Postgresql).
(https://github.com/settor21/myFlix_authDB)
 - For **polyglot persistence**
 - Postgresql for user and session info (salted using bcrypt) - /postgresql branch
 - MongoDB for Metadata (User clicks, user plays) - /mongoDB branch
 * Dockerized versions were deployed to handle requests. A 100GB disk was mounted to ensure persistence of data

Stripe payment test page was used during signup to allow users to pay £5 monthly. 

