# What's the problem?
The pandemic of COVID-19 has brought a change in the frequency and amounts that we donate, resulting in the NGOs and care funds deployed by government or private organizations having a larger influx of money. We intend to tackle the problem of handling such large amounts of money and the corruption that comes with it. We plan to use the blockchain technology to track the funds being donated. It  incentivizes the organizations to use the money as expected ensuring transparency in transactions and in turn motivating public contributions. With the decentralized ledger, all the transactions can be verified making sure no alterations are made in the transactions till the end.

# Demo video 
https://youtu.be/pzh7Hu6ImyU

# The architecture

<a href="http://fvcproductions.com"><img src="https://github.com/arunima811/basic-blockchain-api/blob/master/Architecture.png" alt="FVCproductions"></a>

# Solution description

As mentioned, we deal with a problem statement of transparency in usage of donation funds received by NGOs and government funds that are collected for the betterment of our society. The ultimate solution to this problem can be the use of blockchain and it’s decentralized ledger to prevent tampering with the funds and achieve transparency where the donor can track and analyze the usage of their money. To develop such a revolutionary system, we started implementing the system on python. We have stored the transactions as json and these transactions are packed into blocks. For each transaction, a hash is computed which acts as digital fingerprint. Each block contains the hash of the previous block linked to it. If the data of any block is tampered, it’s has changes resulting in a change of the previous hash of the next block which in turn changes the previous has of next block. Thus, any change in the data of previous blocks would render the entire chain from the tampered block invalid, hence confirming transparency.  Although, after changing the data of a block, the rest of the chain can be re-computed with new hash values resulting in a different valid chain. To prevent this, a proof of work algorithm is implemented. A constraint that hash should have a certain number of leading zeroes is put and a variable number called nonce is computed to get the required hash. The difficulty of the algorithm depends on the number of zeroes used. More the number of zeroes, harder it is to find nonce hence more security. The difficulty level in our deployed system is 2. Now that all the parameters of a transaction has been computed, they are stored as unconfirmed transactions.

# Project roadmap
<a href="http://fvcproductions.com"><img src="https://github.com/arunima811/basic-blockchain-api/blob/master/roadmap.PNG" alt="FVCproductions"></a>

# Run
> Clone the repository and run:
```shell
$ pip install -r requirements.txt
$ python node_server.py
```
