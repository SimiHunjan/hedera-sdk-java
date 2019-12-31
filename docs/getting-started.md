# Getting Started

## Requirements

1. [ ] IDE of your choice \(IntelliJ/Eclipse\)
2. [ ] Hedera Java SDK
3. [ ] JDK 8

## Step 1: Create an account

In order to use the Hedera Public Testnet you’ll need an Account. You can get one by signing up on portal.hedera.com, or maybe a friend who already is on the public testnet can create one for you.

## Step 2: Download the hedera-java-sdk

```text
git clone https://github.com/hashgraph/hedera-sdk-java.git\
```

 or

Download the sdk [here](https://github.com/hashgraph/hedera-sdk-java)

## Step 3: Open the project in your favorite IDE

IntelliJ and Eclipse are popular IDEs that can be used to open the project.

Open the hedera-java-sdk folder

Right click on the pom.xml file in the root directory

Select Open With and select 



### 3. Configure your environment variables

* Locate the **env.sample** file in the root directory
* Edit the following variables
  * `NODE_ID`: the ID of a node in the network \(e.g. 0.0.3\)
  * `NODE_ADDRESS`: the IP address and port that corresponds to the node ID \(e.g. 0.testnet.hedera.com:50211\)
  * `OPERATOR`: your `accountId` in the above network \(e.g. 0.0.3\)
  * `OPERATOR_KEY`: the **private key** associated with the operator `accountId`
* Rename the **env.sample** file to **.env**

### 4. Run SDK examples

* Navigate to **/examples/src/main/java/com/hedera/hashgraph/sdk/examples/simple/**
* Run **CreateAccount.java** file

If you have any issues running the examples, please connect with with us via Discord!

