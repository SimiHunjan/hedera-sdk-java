# Getting Started

In this example, you will do the following:

* [ ] Create a Public Testnet account
* [ ] Download and compile a hedera-sdk-java example file

## Step 1: Create an account

In order to use the Hedera Public Testnet you’ll need an Account. You can get one by signing up on portal.hedera.com, or maybe a friend who already is on the public testnet can create one for you.

Once complete, the following information will be available:

* Public Testnet node ID and node address of the node that will submit your transactions to the network
* Your Public Testnet account ID and private key

## Step 2: Download the hedera-java-sdk

2.1 Visit [https://github.com/hashgraph/hedera-sdk-java/tree/v0.8.0](https://github.com/hashgraph/hedera-sdk-java/tree/v0.8.0) and download the hedera-sdk-java v0.8.0

The hedera-sdk-java should now be in your Downloads folder.

## Step 3: Open the project in your favorite IDE

IntelliJ and Eclipse are popular IDEs that can be used to open the project.

3.1 Open the hedera-java-sdk folder from your Downloads directory

3.2 Right click on the pom.xml file in the root directory

3.3 Select Open and choose your IDE of choice

## Step 4. Configure your environment variables

4.1 Locate the **env.sample** file in the root directory and have your Hedera portal information handy

4.2 Edit the following variables

* `NODE_ID`: the Pubic Testnet node ID \(e.g. 0.0.3\) 
* `NODE_ADDRESS`: the IP address and port that corresponds to the Public Testnet node ID \(e.g. 0.testnet.hedera.com:50211\) 
* `OPERATOR`: your account ID in the Public Testnet \(e.g. 0.0.3\)
* `OPERATOR_KEY`: the private key ****associated with the operator account ID

4.3 Rename the **env.sample** file to **.env**

## Step 5. Run SDK examples

5.1 Navigate to **/examples/src/main/java/com/hedera/hashgraph/sdk/examples/simple/**

5.2 ****Run **CreateAccount.java** file

```java

```



If you have any issues running the examples, please connect with with us via Discord!

