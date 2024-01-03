# Starter Next/Hardhat Project

After cloning the github, you will want to do the following to get the code running on your computer.

1. Inside the project directory, in the terminal type: npm i
2. Open two additional terminals in your VS code
3. In the second terminal type: npx hardhat node
4. In the third terminal, type: npx hardhat run --network localhost scripts/deploy.js
5. Back in the first terminal, type npm run dev to launch the front-end.

After this, the project will be running on your localhost. 
Typically at http://localhost:3000/

### Assessment Contract

- **Solidity Version:** 0.8.9
- **License:** UNLICENSED

#### State Variables
- `owner`: The owner's address
- `balance`: Current contract balance in wei

#### Events
- `Deposit(uint256 amount)`: Triggered on deposit
- `Withdraw(uint256 amount)`: Triggered on withdrawal
- `Reservation(address indexed user, uint256 numberOfPeople)`: Triggered on table reservation

#### Constructor
- `initBalance`: Initial balance for contract deployment

#### Functions
1. `getBalance()`: View function to get the current contract balance.
2. `deposit(uint256 _amount)`: Allows the owner to deposit funds into the contract.
3. `withdraw(uint256 _withdrawAmount)`: Allows the owner to withdraw funds from the contract.
4. `makeReservation(uint256 numberOfPeople)`: Allows users to reserve tables, costing 2 ETH per person.

#### Custom Error
- `InsufficientBalance(uint256 balance, uint256 withdrawAmount)`: Custom error thrown when withdrawing more funds than available.

## DApp (Decentralized Application)

### HomePage Component

#### Dependencies
- `react`: React library
- `ethers`: Ethereum library for interacting with smart contracts
- `Assessment.sol`: Solidity contract artifacts

#### Components
- `ethWallet`: MetaMask wallet instance
- `account`: Connected Ethereum account
- `atm`: Instance of the deployed Assessment contract
- `balance`: Current account balance
- `numberOfPeople`, `depositAmount`, `withdrawAmount`: State variables for reservation, deposit, and withdrawal amounts

#### Functions
1. `getWallet()`: Get MetaMask wallet instance and connected account.
2. `handleAccount(account)`: Set connected account.
3. `connectAccount()`: Connect MetaMask wallet and get a reference to the deployed contract.
4. `getATMContract()`: Set up the ATM contract instance.
5. `getBalance()`: Get and set the current account balance.
6. `deposit()`, `withdraw()`, `reserveTable()`: Interact with the contract for deposit, withdrawal, and reservation.
7. `initUser()`: Initialize user interface based on wallet and account status.

#### Usage
- Displays welcome message, cost per person, and user interface for account management.
- Allows users to connect MetaMask, view balance, reserve tables, deposit, and withdraw funds.

**Note:** Make sure to replace the `contractAddress` and `atmABI` values with the actual deployed contract address and ABI.

Feel free to customize the DApp further based on your project requirements.
