# SimpleAuction.sol
SimpleAuction.sol
pragma solidity ^0.8.20;
contract SimpleAuction {
    address public highestBidder;
    uint public highestBid;

    function bid() public payable {
        require(msg.value > highestBid, "Low bid");
        highestBid = msg.value;
        highestBidder = msg.sender;
    }
}
