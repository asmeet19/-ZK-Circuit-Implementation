# ZK SNARK Designer

## Circum Circuit

This project implements a zkSNARK circuit to prove knowledge of the inputs A and B that yield a 0 output. We utilize the circom programming language to define the circuit and ZoKrates to generate the proof and verification keys. Finally, we deploy a verifier smart contract on-chain to verify the proofs generated by the zkSNARK circuit.

## Description

The circuit implements the following truth table:

| A | B | X | Y | Q |
|---|---|---|---|---|
| 0 | 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 0 | 1 |

## Project Implementation

1. Write a correct `circuit.circom` implementation.
2. Compile the circuit to generate circuit intermediaries.
3. Generate a proof using inputs A=0, B=1.
4. Deploy a Solidity verifier to Goerli/Mumbai Testnet.
5. Call the `verifyProof()` method on the verifier contract and assert output is true.

## Steps

1. **Install Dependencies:** 
   Run `npm install` to install the required dependencies.

2. **Update Hardhat Configuration File:**
   Ensure your Hardhat configuration file is updated correctly.

3. **Compile the Contract:**
   Execute `npx hardhat compile` to compile the contract.

4. **Deploy the Contract:**
   Run `npx hardhat run scripts/deploy.ts` to deploy the contract.

5. **Verify the Deployment:**
   After successful deployment, the script `deploy.ts` should print "true" in the terminal if deployment is successful. If any issues arise, review your contract code and the Hardhat configuration.
   Remember to use a `.env` file to store private keys securely. However, avoid committing the `.env` file to version control systems to prevent leaking sensitive information. Also, exercise caution when deploying contracts and ensure thorough testing before deploying to the mainnet or any production environment.

## Author
Asmeet
