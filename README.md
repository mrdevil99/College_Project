# Aadhaar Voting
Aadhaar Bassed voting system using blockchain technology
Project implemented as part of Rajasthan Hackathon

## Description

* The authority must log in first with the provided session ID.
* The voter can now begin the process of voting with proper authentication through OTP(one-time password) on the respective linked mobile number.
* If the voter is valid then the system will check for the voter's age and the address to which he can give a vote.
* The voting pallet will be opened with  candidate names, their parties, and logos.
* Now the voter can give his vote by clicking the vote button.
* one voter can give his vote only once, i.e. after one time voting buttons are disabled and the vote is automatically logged out.
* The same process continues for many more voters irrespective of their voting wards.

### Installing and Running Project

Clone Project
```
git clone git@github.com:sanattaori/techdot.git && cd techdot
```
Install Dependencies
```
npm install
```
Running Project
```
node index.js
```
If a dependency problem occurs delete package.json, Run
```
npm init
```
Again Install dependencies and run the project.


### Running Project
Step 1 - Setting up the Environment
Instead of developing the app against the live Ethereum blockchain, we have used an in-memory blockchain (think of it as a blockchain simulator) called testrpc.

```
npm install Ethereum-testrpc web3
```

Step 2 - Creating a Voting Smart Contract

```
npm install solc
```

Replace your aadhaar no and phone number for running the project at https://github.com/mrdevil99/College_Project/blob/main/ui/js/app.js#L39

Step 3 - Testing in the node console

Not required just for testing in node console-
After writing our smart contract, we'll use Web3js to deploy our app and interact with it
```
$ node
> Web3 = require('web3')
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
Then ensure Web3js is initalized and can query all accounts on the blockchain

> web3.eth.accounts
Lastly, compile the contract by loading the code from Voting.sol in to a string variable and compiling it

> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)
```
testrpc creates 10 test accounts to play with automatically. These accounts come preloaded with 100 (fake) ethers.

Deploy the contract!

dCode.contracts[‘: Voting’].bytecode: bytecode which will be deployed to the blockchain.
compiled code. contracts[‘:Voting’].interface: the interface of the contract (called abi) which tells the contract user what methods are available in the contract.
```
> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)
> VotingContract = web3.eth.contract(abiDefinition)
> byteCode = compiledCode.contracts[':Voting'].bytecode
>deployedContract = VotingContract.new(['Sanat','Aniket','Mandar','Akshay'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
> deployedContract.address
> contractInstance = VotingContract.at(deployedContract.address)
deployedContract.address. When you have to interact with your contract, you need this deployed address and abi definition we talked about earlier.
```
Step 4 - Interacting with the Contract via the Nodejs Console
```
> contractInstance.totalVotesFor.call('Sanat').toLocaleString()
'2'
```

### For TypeError: Cannot read property ': Voting' of undefined :
Make sure you have ganache-cli
```
sudo npm install ganache-cli -g
```
copy address of the first account
```
$ ganache-cli
```
Paste this address to 
ui/js/clist.js line 17
https://github.com/mrdevil99/College_Project/blob/main/ui/js/clist.js #17


### Purpose of the test

 * The authority login is to ensure security to prevent piracy, harassment, and corruption from candidates standing in the election.
 * OTP generation is to authenticate the right Aadhar card owner.
 * button disabling and automatic logout are to prevent multiple voting by a single candidate.

   
### Screenshots
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/1.PNG)
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/2.PNG)
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/3.PNG)
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/4.PNG)
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/5.PNG)
* ![](https://github.com/mrdevil99/College_Project/blob/main/screenshot/gan.PNG)

## Deployment

The Aadhaar-based voting system was developed to overcome the flaws of the EVM system. So directly EVM will be replaced by a screen interface the great
user interface and high security.

