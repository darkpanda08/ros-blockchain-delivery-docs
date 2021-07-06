Using the given Network
########################

Now that you have downloaded Fabric and the samples, you can start running Fabric.

After you have downloaded the Hyperledger Fabric Docker images and samples, you can deploy a test network by using scripts that are provided in the ``fabric-samples`` repository. The test network is provided for learning about Fabric by running nodes on your local machine. Developers can use the network to test their smart contracts and applications. The network is meant to be used only as a tool for education and testing and not as a model.

Bring up the test network
*************************

First thing before making a blockchain application is to create a blockchain network.
1. To bring up the network go inside test-network directory using ``cd fabric-samples/test-network`` command.
2. From inside the test-network directory, run the following command to remove any containers or artifacts from any previous runs: ``./network.sh down``
3. You can then **bring up the network** by issuing the following command. You will experience problems if you try to run the script from another directory: ``./network.sh up``
4. After your test network is deployed, you can take some time to examine its components. Run the following command to list all of Docker containers that are running on your machine. You should see the three nodes that were created by the network.sh script: ``docker ps -a``

Creating a channel
******************
You can use the network.sh script to create a channel between Org1 and Org2 and join their peers to the channel. Run the following command to create a channel with the default name of mychannel: 

``./network.sh createChannel``

You can also use the channel flag to create a channel with custom name. As an example, the following command would create a channel named channel1: 

``./network.sh createChannel -c channel1``

If you want to bring up the network and create a channel in a single step, you can use the up and createChannel modes together:

``./network.sh up createChannel``


When inside test-network directory run this command ``export PATH=${PWD}/../bin:$PATH``

Using the fabcar chaincode
**************************
Inside fabric-samples there is a sample chaincode for fabcar. We will using that chaincode here.

1. Go inside fabcar directory using ``cd fabcar``
2. Explore the contents of ``startFabric.sh``. This file creates a network and channel as we created eariler in test-network directory. It also deploys a chaincode present in ``fabric-samples\chaincode\fabcar``
3. fabcar can be deployed using any of three languages between go, java and javascript. We will be using go for the same. For that run the following command ``./startFabric.sh go``.
4. After successful deployment instructions for using fabcar will be printed on the terminal. Use command ``cd go`` to and use go language. 