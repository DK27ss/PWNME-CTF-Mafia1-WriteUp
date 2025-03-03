# PWNME-CTF-Mafia1-WriteUp

## Overview
During the first PWNME qualifications in this weekend, there were some pretty cool challenges. So I'm doing a write-up of some of them to deepen my skills and share my results with you.
In this first challenge we simply receive a wireshark capture file and we know that the data contained inside is the result of an exchange on a poorly-secured chat, allowing us to view the messages in clear text.

![mafia1_1](https://github.com/user-attachments/assets/eff59aa5-da6e-4dd6-b770-d6b166f5a676)

So I start by `filtering` out interesting frames using only the `IRC` protocol, which seems to contain the exchanges

![mafia1_irc2](https://github.com/user-attachments/assets/cac38ee0-75d3-4033-a887-6169a88f8f60)

while checking the content of messages exchanged on `IRC (Internet Relay Chat)` I came across an interesting capture referring to an `smart contract address`

![mafia1_content1](https://github.com/user-attachments/assets/087f0bf5-3b12-4954-8ab9-8ad8dc792511)

taking into account the clue in the statement which clearly explains that the contract is deployed on the `sepolia chain`, I can then check the relevant information for this contract.

At this point, by searching on `sepolia.etherscan.io`, we obtain the following information thanks to the `contract address` `https://sepolia.etherscan.io/tx/0x2a1133ebd2476d670b2b1668f7db32774e02533b8ca9f2e1a98a9a67b9dd9165`

![mafia1_etherscan](https://github.com/user-attachments/assets/6681a2b3-8282-4b29-8541-86a44ba15820)

we can then display more information with (Show more) and change the `Input Data` display method

![mafia1_etherscan1](https://github.com/user-attachments/assets/5370c7b5-6ba5-4727-a2a9-3b55d6091fdc)

Finally, when we use `UTF-8` for display, we get the flag !

![mafia1_etherscan2](https://github.com/user-attachments/assets/4249cbf0-954b-4964-8b36-519ef626e861)

