# Assessment Smart Contract

This Solidity smart contract, named "Assessment," is designed to handle various financial transactions and ticket purchases. It is implemented in Solidity version 0.8.9.

## Contract Details

After cloning the github, you will want to do the following to get the code running on your computer.

1. Inside the project directory, in the terminal type: npm i
2. Open two additional terminals in your VS code
3. In the second terminal type: npx hardhat node
4. In the third terminal, type: npx hardhat run --network localhost scripts/deploy.js
5. Back in the first terminal, type npm run dev to launch the front-end.

After this, the project will be running on your localhost. 
Typically at http://localhost:3000/

### State Variables
- `owner`: The address of the contract owner, initialized as the deployer.
- `balance`: The current balance of the contract in wei.

### Ticket Prices
- `economyTicketPrice`: The price of an economy class ticket, set to 10 wei.
- `businessTicketPrice`: The price of a business class ticket, set to 15 wei.

### Events
- `Deposit(uint256 amount)`: Triggered when a deposit is made.
- `Withdraw(uint256 amount)`: Triggered when a withdrawal is made.
- `TicketBought(string ticketType, uint256 price)`: Triggered when a ticket is bought.

### Constructor
The constructor initializes the contract with an initial balance, provided during deployment.

### Functions
1. `getBalance()`: Returns the current balance of the contract.
2. `deposit(uint256 _amount)`: Allows the owner to deposit funds into the contract.
3. `withdraw(uint256 _withdrawAmount)`: Allows the owner to withdraw funds from the contract.
4. `buyTicket(string memory ticketType)`: Allows users to buy tickets with specified types.

## Custom Error
- `InsufficientBalance(uint256 balance, uint256 withdrawAmount)`: Custom error thrown when attempting to withdraw more funds than available.

## Development

### Deployment Script
The deployment script (`deploy.js`) initializes the contract with a specified initial balance and deploys it on the Ethereum blockchain using Hardhat.

### Usage
To deploy the contract, run the deployment script:
```bash
npx hardhat run deploy.js
```

