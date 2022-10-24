// SPDX-License-Identifier: MIT
pragma solidity ^0.8.4;

contract SmartBank{
//map for storing wallet address and its funds sent to this smart contract.
mapping(address=>uint) public accountwallet;
  
  //modifier to check if the wallet has min balance
    modifier balancecheck(uint amt) {
        require(amt<=accountwallet[msg.sender],"Low balance");
        _;
    }
    //a function to deposit funds to the smartcontract wallet;
    function depositfunds() public payable{
        accountwallet[msg.sender]+=msg.value;
    }
    //a function to transfer the ether back in to wallet;
    function withdrawfunds(uint amt) public  balancecheck(amt){
        payable(msg.sender).transfer(amt);
    }
    //a function to know te total balance of smart contract.
    function totalbalance() public view returns(uint){
        return address(this).balance;
    }
}
