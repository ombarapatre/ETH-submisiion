## TOKEN.SOL
This is a basic Solidity smart contract for a token called "Token". 

## DESCIRPTION
The code is a Solidity smart contract for a basic token called "MyToken". It also has two public variables for the token name and abbreviation, and a total supply variable. It also has a mapping variable called "balances" which maps addresses to their token balances.
This contract has two functions called "mint" and "burn". The "mint" function  adds the given value to the balance of the specified address. The "burn" function  reduces the balance of the specified address by the given value, but only if the address has sufficient balance.

## GETTING STARTED
We have to use remixIDE to compile and run and deploy the program.

## EXECUTING THE PROGRAM
* Create a new folder named mytoken.sol.
* Write the contract in Solidity.
* If the Remix is on auto compile and run, the written code will be compiled and run automatically. However, if it is not on auto compile, we have to manually compile and run the code by selecting the option "Compile and Run" in the left menu.
* After compiling, we deploy the contract, and then we get the account address which we use in further steps.
* Once the code is deployed successfully, we can check the token name and token abbreviation we have given in the code.
* By clicking on "tokenabbvr," we can check the token abbreviation, and similarly, we can check the token supply and token name too.
* Initially, we will have 0 balance in our account.
* For minting, we click on the "mint" button, then we paste the account address , and then we put the value of how many tokens we have to mint. Let's take 100 tokens, then click "transact."
* To check the balance, click on "balances," then paste the account address and click on "call." We will get the account balance.
* Then, to burn some tokens, click on "burn," and then paste the account address, and then set the value to 70 .
* To check the balance again, press "call," and we will get the latest balance. 100 - 70 = 30 .
* This is all for the contract.

## CONTRACT 

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


contract MyToken {

    // public variables here
   string public tokenName ="MRUNAL";
   string public tokenAbbvr= "MRU";
   uint public totalSupply=0;
    // mapping variable here
   mapping(address=> uint) public balances;
    // mint function

   function mint (address _address, uint _value) public {
    totalSupply +=_value;
    balances[_address] += _value;
   }
    // burn function
   function burn (address _address,uint _value) public {
       if(balances[_address]>=_value)
       {
         totalSupply -=_value;
         balances[_address] -= _value;
       }
    
   }
}
