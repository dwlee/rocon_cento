cento_server
============

## Quick Start

    git clone git@github.com:robotics-in-concert/rocon_cento.git
    cd rocon-cento/app
    mrt

## Pre-requisites

 - [node/npm](http://nodejs.org/download/)
 - [git](http://git-scm.com/downloads)
 - [Meteor](http://docs.meteor.com)
 - [Meteorite](https://atmospherejs.com/docs/installing)

### Recommended Install on Ubuntu Precise 12.04

    sudo add-apt-repository ppa:chris-lea/node.js
    sudo apt-get update
    sudo apt-get install python-software-properties python g++ make nodejs curl
    curl https://install.meteor.com | /bin/sh
    sudo npm install -g meteorite
    sudo rm -Rf ~/tmp
    
### Run on a private machine

 - Register application to Github (https://github.com/settings/applications)
  - Fill Homepage URL and Authorization callback URL form:
    - Homepage URL: http://localhost:3000
    - Authorization callback URL: http://localhost:3000/_oauth/github?close
 - Connect to mongoDB and insert login service configuration
  
    ``` 
    use cento
    db.meteor_accounts_loginServiceConfiguration.insert({ "_id" : "Arbitary Value like(S5mtDCFeruAAEgSnC)",
    "service" : "github", "clientId" : "Your Client ID", "secret" :
"Your Client Secret" })
    ```
 - Run
 
  ``` ROOT_URL=Your URL:Port MONGO_URL=mongodb://localhost:27017/cento mrt ```
 

