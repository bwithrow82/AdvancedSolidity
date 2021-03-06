# AdvancedSolidity
Advanced Solidity Homework
I created a crowdsale contract using Solidity for the "PupperCoin" token. The goal amount for the crowdsale is 300 Ether and will last 24 weeks.

Some crowdsale contract features:

An ERC20 token will be created and be minted through a Crowdsale contract that can be leveraged from the OpenZeppelin Solidity library.
This crowdsale contract manages the entire process, allowing users to send ETH and get back PUP (PupperCoin).
This contract will mint the tokens automatically and distribute them to buyers in one transaction.
The crowdsale contract inherits from Crowdsale, CappedCrowdsale, TimedCrowdsale, RefundableCrowdsale, and MintedCrowdsale.
The crowdsale will be conducted on the Kovan testnet in order to get a real-world pre-production test in.
PupperCoin.sol file creates a standard ERC20Mintable token. It uses an ERC20Detailed contract.

Crowdsale.sol file takes in the following parameters:

rate - rate in TKNbits
wallet - sale beneficiary
goal - cap of the crowdsale
openingTime - is set equal to now
closingTime - is set equal to now + 24 weeks
As mentioned previously, this contract inherits from the following OpenZeppelin contracts:

Crowdsale - takes in rate, wallet, and token as parameters
CappedCrowdsale - takes in goal as a parameter
TimedCrowdsale - takes in openingTime and closingTime as parameters
RefundableCrowdsale - takes in goal as a parameter
MintedCrowdsale
It is important to note that the RefundableCrowdsale constructor is called instead of the RefundablePostDeliveryCrowdsalecontract because RefundablePostDeliveryCrowdsale inherits the RefundableCrowdsale constructor.

Testing the Crowdsale
Connect to a test network such as Kovan or Ropsten
Fund your account using a test faucet
Compile Crowdsale.sol and deploy PupperCoinSaleDeployer from the contract dropdown menu.
Under deploy, set name to "puppercoin", symbol as "pup", wallet as the address of your Metamask and goal to 300.
image

Hit Transact and hit confirm on the Metamask popup.
Under Deployed Contracts, copy the value given for token_address
image

Select PupperCoin from the contract dropdown menu and paste the token address to At Address field then click the At Address button.
Copy the token_sale_address from the PupperCoinSaleDeployer deployed contract and switch the contract to PupperCoinSale then paste the token_sale_address into the AT Address field and click At Address button.
Under Deployed Contracts, expand the PupperCoinSale contract and enter an address from Ganache as the beneficiary under buyTokens.
image

Change to desired value and transact.
