This file contains the steps I use to create the sioe and deploy it.

#### 1. Installation
For the installation I used the Recommended approach from here https://github.com/alshedivat/al-folio/blob/master/INSTALL.md#installing-and-deploying

#### 2. Local work
to work on a local copy and check the tests before deployng the website, I used the docker (https://github.com/alshedivat/al-folio/blob/master/INSTALL.md#local-setup-using-docker-recommended)

The first time, it is necessary to download the docker image
$ docker compose pull

Afterwards, to work on the local website, need to start the docker
$ docker compose up
This will not only launch the locak website, but any change to the code will automatically update it

#### 3. Deploy
To deploy the website it is enough to commit and push the repo

WARNING>: msut not push the Gemfile.lock, as this breaks the deployment.
may also use the command
$ bundle lock --add-platform x86_64-linux

