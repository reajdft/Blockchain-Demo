# Blockchain-Demo
Step by step instructions for developing a crypto-currency using Geth Tools v1.9.7 and MyCrypto Wallet
## Step 1: Download "Geth & Tools 1.9.7"
![Geth Install](screens/1a.png)
After clicking on the link and thus downloading the file, unzip and "save as" the name of your coin (in this example and ensuing images, we'll be using "kdoag")
## Step 2: Blockchain Parameter Definition 
We'll be selecting "Proof of Work" in this example given it's general adoption in the market:![Puppeth](screens/step1.png)
## Step 3: MyCrypto Key Assignment
Copy your public key from your MyCrypto wallet ![Keys](screens/Keys.png)And save into a working text file (example below) ![Example](screens/examplenotes.png)in which you'll be logging keys, passwords, etc for quick retrieval
And lastly, assign your wallet to the blockchain to populate test currency found later in this tutorial. Continue pressing "enter" and pre-populating with Wei until you arrive at the key assignment prompt![keyinputs](screens/publickeyselection.png)
## Step 4: Chain ID
Assign a Chain ID (must be an integer) and record in your text file for access later![CID](screens/chainid.png)
## Step 5: Genesis Configuration
Congrats, we got this bitch configured!![Genesis](screens/genesisconfig.png)
## Step 6: Let's Mine this KDOAG!
Just kidding, we'll actually just create our mining node (Node 1) using this command: ./geth account new --datadir node1![Node1](screens/node1.png)

And next we'll do the same for our ledger node (Node 2) using this command ./geth account new --datadir node2

**REMEMBER TO LOG YOUR PASSWORDS AND KEYS FOR BOTH NODES**

## Step 7: Node Initializing
Using this command, initialize your mining node: "./geth init yournetworkname.json --datadir node1" ![Node1activate](screens/miningnode.png)
Perform the same command for node 2 after initializing node 1 "./geth init yournetworkname.json --datadir node2"
## Step 8: And now we mine ourselves some KDOAG
Run the following command: "./geth --datadir node1 --mine --minerthreads 1" instrucing the node to mine new blocks and how many "workers" we'll be utilizing - in this case for sake of simplicity and preserving our CPUs processing power, we'll select "1" ![mining](screens/mining.png)

Soon after launching the mining process, you'll need to grab the enode displayed a few seconds in - copy and paste into your recorder file

![miningoutput](screens/miningoutput.png)

## Step 9: Launch the ledger node
Open a new terminal window and run the following command: "./geth --datadir node2 --port 30304 --rpc --bootnodes "enode://<replace with node1 enode address>"
Your command should look something like this: ![examplenode2command](screens/examplenode2.png)
And should render something that looks like this: ![examplenode2output](screens/step9.png)
## Step 10: Status Check
At this point, with both terminals open you should have a process running that appears similar to this ![blockchainrunning](screens/example1.png), with the left window mining new blocks and the right window recording the blocks
## Step 11: MyCrypto Creation
In the MyCrypto UI you'll then create a new coin ![new coin](screens/step11.png)

With evidence of your new coin situated in left nav bar as follows: ![visual](screens/step12.png)

