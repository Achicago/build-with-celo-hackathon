# ⚡ CarbonX on Celo Blockchain ⚡                                                                                                                                                                                                        
# CarbonX Decentralized Application: CarbonX (ReFi) 
![banner](https://github.com/Achicago/build-with-celo-hackathon/blob/master/CarbonX/server/public/images/logo.png)

- CarbonX Everything Regenerative Finance (ReFi)


  # 💡 Where do we get ideas ?
       Decentralized applications developed using blockchain technology provide innovative business models to serve the human race 
      and solve existing challenges. Climate change is one of the biggest problems humanity is facing and there is a dearth of solutions in 
      tackling  this  grave  impediment to the long-term sustainability  of our  planet. Accountability,  greenwashing, traceability, impact 
      assessment and trading of carbon credits are unresolved issues in the  ESG sector. In this paper, we present a novel decentralized 
      application  software, CarbonX,  that  solves the  enumerated  problems using  NFTs  on the  blockchain  platform, through  smart 
      contracts.  The  paper describes the  functional  architecture  of CarbonX,  while  elaborating  on its  salient  features  and utility  in 
      sustainable  finance,  in  particular  green  sukuk.  CarbonX  is  a  pioneering  software  providing  an  exchange  for  trading  of  carbon 
      credits.  The software facilitates logging  of  impact and  traceable  transactions  in  a carbon  market,  that  would help  to  prevent 
      duplication of records and greenwashing. The paper discusses the efforts being undertaken to achieve the climate goals as per the 
      Paris Agreement and  also highlights the pivotal  obstacles to  achieving carbon  neutrality by  2050, as per  COP26. The  paper also 
      encompasses a study on the applications of dapps in DeFi, Web 3.0 and ESG, among other areas and gives  a comparative analysis 
      of  blockchain  platforms  for  dapp  development.  The  paper  is  also  a  pioneer  in  highlighting  the  challenges  that  plague  dapp 
      development, deployment and usage. 
# Index Terms 
   DIFC, blockchain, dapps, COP26, Celo, CarbonX, ESG, Web 3.0, climate     change, carbon market, greenwashing, NFT


# Solidity Code ( Contract Address : 0x30C06ac9FCAfD569e62bc40e5EB39a32495BbE5C )
    // SPDX-License-Identifier: MIT
        pragma solidity ^0.8.4;

        import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
        import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
        import "@openzeppelin/contracts/security/Pausable.sol";
        import "@openzeppelin/contracts/access/AccessControl.sol";
        import "@openzeppelin/contracts/token/ERC20/extensions/draft-ERC20Permit.sol";
        import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Votes.sol";

        contract CarbonX is ERC20, ERC20Burnable, Pausable, AccessControl, ERC20Permit, ERC20Votes {
            bytes32 public constant PAUSER_ROLE = keccak256("PAUSER_ROLE");
            bytes32 public constant MINTER_ROLE = keccak256("MINTER_ROLE");

            constructor() ERC20("CarbonX", " CabX") ERC20Permit("CarbonX") {
                _grantRole(DEFAULT_ADMIN_ROLE, msg.sender);
                _grantRole(PAUSER_ROLE, msg.sender);
                _grantRole(MINTER_ROLE, msg.sender);
            }

            function pause() public onlyRole(PAUSER_ROLE) {
                _pause();
            }

            function unpause() public onlyRole(PAUSER_ROLE) {
                _unpause();
            }

            function mint(address to, uint256 amount) public onlyRole(MINTER_ROLE) {
                _mint(to, amount);
            }

            function _beforeTokenTransfer(address from, address to, uint256 amount)
                internal
                whenNotPaused
                override
            {
                super._beforeTokenTransfer(from, to, amount);
            }

            // The following functions are overrides required by Solidity.

            function _afterTokenTransfer(address from, address to, uint256 amount)
                internal
                override(ERC20, ERC20Votes)
            {
                super._afterTokenTransfer(from, to, amount);
            }

            function _mint(address to, uint256 amount)
                internal
                override(ERC20, ERC20Votes)
            {
                super._mint(to, amount);
            }

            function _burn(address account, uint256 amount)
                internal
                override(ERC20, ERC20Votes)
            {
                super._burn(account, amount);
            }
        }


# Deployment of CarbonX ("CabX") on Alfajores Testnet Successful ✅

![top](https://github.com/Achicago/build-with-celo-hackathon/blob/master/CarbonX/server/public/images/Screenshot%20(103).png)   

![top](https://github.com/Achicago/build-with-celo-hackathon/blob/master/CarbonX/server/public/images/Screenshot%20(104).png)   

# CarbonX Transactions on Celo Blockchain

![top](https://github.com/Achicago/build-with-celo-hackathon/blob/master/CarbonX/server/public/images/transact.png)   

![top](https://github.com/Achicago/build-with-celo-hackathon/blob/master/CarbonX/server/public/images/transaction.png)   




