# HyperledgerFabric1
This project is to implement between Blockchain and API for data storage. Hyperledger Fabric is referred to alternative blockchain solution. It is a platform for distributed ledger to support pluggable implementation of different components. Please see more detail about Hyperledger Fabric at https://hyperledger-fabric.readthedocs.io/en/release-2.2/



Installation:

```
sudo apt-get update
```

Install cURL
Download the latest version of the cURL tool if it is not already installed or if you get errors running the curl commands from the documentation.
 ```
 sudo apt-get install curl
curl –version
```

Docker and Docker Compose
You will need the following installed on the platform on which you will be operating, or developing on (or for), Hyperledger Fabric.

Install the latest version of Docker from the official Docker repository
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Add the Docker repository to APT sources
```sudo add-apt-repository “deb [arch=amd64] 
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable”
```

Update the package database
```
sudo apt-get update
```

Docker compose:
you must install with the following command from a terminal prompt:
```
sudo apt-get install -y docker-ce
```

•	Test the Installation
Check the docker and docker-compose version
```
docker --version
docker-compose –version
```

Pull the hello-world image from Docker Hub and run a container:
```
docker run hello-world
```

Go language
For this work, we use Go 1.14.2 version which implement chaincode deployment, go to official site Downloading: https://golang.org/dl/. 

![image](https://user-images.githubusercontent.com/74609915/122907415-7798f480-d396-11eb-93b2-ec3075d1a8c1.png)

Then follow its installation instructions:
Extract the archive you downloaded into /usr/local, creating a Go tree in /usr/local/go.
Important: This step will remove a previous installation at /usr/local/go, if any, prior to extracting. Please back up any data before proceeding.
For example, run the following as root or through sudo:

```
tar -xvf go1.14.2.linux-amd64.tar.gz
```

Then, move the folder to /usr/local.
```
sudo mv go /usr/local
```

Now, we have to set some paths that Go needs. The paths given in this step are all relative to the location of the Go installation in /usr/local.
```
Export PATH=$PATH:/usr/local/go/bin
```

Verifying
```
go version
```

Nodejs and npm
If you will be developing applications for Hyperledger Fabric leveraging the Hyperledger Fabric SDK for Node.js, version 8 is supported from 8.9.4 and higher. Node.js version 10 is supported from 10.15.3 and higher.
Download the installation script using curl

```
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
```

Run the script under sudo
```
sudo bash nodesource_setup.sh
```

•	Install node js
```
sudo apt-get install nodejs
```

•	Install npm
```
sudo apt-get install npm
```

Python 2.7
By default, Ubuntu 16.04 comes with Python 3.5.1 installed as the python3 binary. The Fabric Node.js SDK requires an iteration of Python 2.7 for npm install operations to complete successfully. Retrieve the 2.7 version with the following command:

```
sudo apt-get install python
```

Check your version(s):
```
python --version
```

Install Samples, Binaries and Docker Images
Determine a location on your machine where you want to place the fabric-samples repository and enter that directory in a terminal window. The command that follows will perform the following steps:
1.	If needed, clone the hyperledger/fabric-samples repository
2.	Checkout the appropriate version tag
3.	Install the Hyperledger Fabric platform-specific binaries and config files for the version specified into the /bin and /config directories of fabric-samples
4.	Download the Hyperledger Fabric docker images for the version specified
Once you are ready, and in the directory into which you will install the Fabric Samples and binaries, go ahead and execute the command to pull down the binaries and images.

Open the directory where you want to download the fabric samples in the terminal.
```
curl -sSL http://bit.ly/2ysbOFE | sudo bash -s 2.1.0
```

If you have completed these steps and find that you are still having problems with the permissions error, then you'll need to allow more access to the docker.sock file. This can be done using the following command.

```
sudo chmod 666 /var/run/docker.sock
```

Generate Network Artifacts
Before we begin, if you haven’t already done so, you may wish to check that you have all the Prerequisites installed on the platform(s) on which you’ll be developing blockchain applications and/or operating Hyperledger Fabric.
You will notice that there are a number of samples included in the fabric-samples repository. We will be using the first-network sample. Let’s open that sub-directory now.

```
cd fabric-samples/first-network
```

They provide a fully annotated script — byfn.sh — that leverages these Docker images to quickly bootstrap a Hyperledger Fabric network that by default is comprised of four peers representing two different organizations, and an orderer node. It will also launch a container to run a scripted execution that will join peers to a channel, deploy a chaincode and drive execution of transactions against the deployed chaincode.

```
./byfn.sh generate
```

Then, you will see a brief description as to what will occur, along with a yes/no command line prompt. Respond with a y or hit the return key to execute the described action.

Bring Up the Network
Next, you can bring the network up with one of the following commands:
```
./byfn.sh up
```

Once again, you will be prompted as to whether you wish to continue or abort. Respond with a y or hit the return key:
![image](https://user-images.githubusercontent.com/74609915/122908035-0ad22a00-d397-11eb-9da4-637d55843dca.png)

The logs will continue from there. This will launch all of the containers, and then drive a complete end-to-end application scenario. Upon successful completion, it should report the following in your terminal window:
![image](https://user-images.githubusercontent.com/74609915/122908061-1291ce80-d397-11eb-8c78-9b963f086993.png)

Bring Down the Network
Finally, let’s bring it all down so we can explore the network setup one step at a time. 
**The following will kill your containers, remove the crypto material and four artifacts, and delete the chaincode images from your Docker Registry:
```
./byfn.sh down
```



