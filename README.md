# What's the problem?
The pandemic of COVID-19 has brought a change in the frequency and amounts that we donate, resulting in the NGOs and care funds deployed by government or private organizations having a larger influx of money. We intend to tackle the problem of handling such large amounts of money and the corruption that comes with it. We plan to use the blockchain technology to track the funds being donated. It  incentivizes the organizations to use the money as expected ensuring transparency in transactions and in turn motivating public contributions. With the decentralized ledger, all the transactions can be verified making sure no alterations are made in the transactions till the end.

# Demo video 
https://youtu.be/pzh7Hu6ImyU

# The architecture

<a href="http://fvcproductions.com"><img src="https://github.com/arunima811/basic-blockchain-api/blob/master/Architecture.png" alt="FVCproductions"></a>

# Solution description

As mentioned, we deal with a problem statement of transparency in usage of donation funds received by NGOs and government funds that are collected for the betterment of our society. The ultimate and revolutionary solution to this problem can be the use of blockchain and it’s decentralized ledger to prevent tampering with the funds and achieve transparency where the donor can track and analyze the usage of their money. We started implementing Trust and Donate on python. We have stored the transactions as json and these transactions are packed into blocks. For each transaction, a hash is computed which acts as digital fingerprint. Each block contains the hash of the previous block linked to it. If the data of any block is tampered, it’s has changes resulting in a change of the previous hash of the next block which in turn changes the previous has of next block. Thus, any change in the data of previous blocks would render the entire chain from the tampered block invalid, hence confirming transparency.  Although, after changing the data of a block, the rest of the chain can be re-computed with new hash values resulting in a different valid chain. To prevent this, a proof of work algorithm is implemented. A constraint that hash should have a certain number of leading zeroes is put and a variable number called nonce is computed to get the required hash. The difficulty of the algorithm depends on the number of zeroes used. More the number of zeroes, harder it is to find nonce hence more security. The difficulty level in our deployed system is 2. Now that all the parameters of a transaction has been computed, they are stored as unconfirmed transactions. To mine these transactions, they are stored as blocks and their correct POW is computed. To add a block to the blockchain, values of POW is checked and the integrity of the chain, i.e. the order of previous hash and next blocks is checked. If both the conditions are verified, the block gets added to the chain. This system is shared to different nodes that are aware of each other’s presence and can contribute to the blockchain. This feature gives the entire system the property of being decentralized. This marks the implementation of complete blockchain. 
Now that our blockchain is ready, we need an interface for the nodes to interact with. Our frontend starts with a Progressive Web App(PWA) using React as the front-end. The home page contains the list of all the organizations associated with our app. The user can login to see their dashboard. A list of all the organizations the user is interested in or the blockchains that the user is a part of are displayed. The user can access the blockchain of the any of those organizations. The app is now redirected to the page that uses the python microframework called Flask to create a REST API that interacts with and invokes various operations in our blockchain node. An initial fund pool of the chosen organization is displayed along with the ability to donate for the users that are donors and to withdraw for the users that are associated with the organization. On submitting the amount, the data is stored as unconfirmed transaction. When request to mine is invoked, the data is sent for computing POW and the block gets mined. The update blockchain function then checks if the POW is correct and the previous hash of the block matches the hash of the last block of the chain and after the conditions are verified, the blockchain is updated with timestamp. 

# Project roadmap
<a href="http://fvcproductions.com"><img src="https://github.com/arunima811/basic-blockchain-api/blob/master/roadmap.PNG" alt="FVCproductions"></a>

# Run
> Clone the repository and run:
```shell
$ pip install -r requirements.txt
$ python node_server.py
```
