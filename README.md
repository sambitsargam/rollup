
## Deployment Overview 

## RPC to Test: https://rollup-sam.railway.app

### 1. Contract Deployment

Contracts are deployed with a maximum data size of 104857. During deployment, several key contracts are created, including:

- **Bridge**
- **SequencerInbox**
- **Inbox**
- **RollupEventInbox**
- **Outbox**
- **ERC20Bridge**
- **ERC20Inbox**
- **ERC20RollupEventInbox**
- **ERC20Outbox**
- **BridgeCreator**
- **OneStepProver0 / OneStepProverMemory / OneStepProverMath / OneStepProverHostIo**
- **OneStepProofEntry**
- **ChallengeManager** (note: this contract may require the `--contract` parameter due to multiple matching bytecodes)
- **RollupAdminLogic**
- **RollupUserLogic**
- **ValidatorUtils**
- **ValidatorWalletCreator**
- **RollupCreator**
- **DeployHelper**
- **RollupProxy**

Each contract is submitted for source code verification on the block explorer. Verification results and links (e.g., on [Sepolia Arbiscan](https://sepolia.arbiscan.io/)) are provided in the logs.

> **Note:**  
> Before starting the deployment, ensure that the `ESPRESSO_LIGHT_CLIENT_ADDRESS` environment variable is set. This is required to deploy the `RollupCreator` for the Espresso integration.

### 2. Rollup Creation

Once the contracts are deployed, the rollup is created by calling the `createRollup` function. The rollup process includes:

- Creation of the **RollupProxy** contract.
- Deployment of associated proxy contracts such as:
  - **Inbox (proxy)**
  - **Outbox (proxy)**
  - **rollupEventInbox (proxy)**
  - **ChallengeManager (proxy)**
  - **AdminProxy**
  - **SequencerInbox (proxy)**
  - **Bridge (proxy)**
- Verification of the rollup proxy contracts.
- Recording the block number at which all contracts are deployed.

The final output includes a congratulatory message with all the deployed addresses and the rollup creation transaction ID, which can be viewed on the block explorer. For example, the transaction is available at:
[https://sepolia.arbiscan.io/tx/0xb65ea0a5463ea7d68b92f025fd649dc1a24ea3bfd78be0c11dc06a554c35c8c8](https://sepolia.arbiscan.io/tx/0xb65ea0a5463ea7d68b92f025fd649dc1a24ea3bfd78be0c11dc06a554c35c8c8).

---

## Deployed Contract Addresses

### Contract Deployment Addresses

| Contract Name              | Address                                                        |
|----------------------------|----------------------------------------------------------------|
| Bridge                     | `0x45a448fDE90562Cb29654505716A6575B8e434c1`                   |
| SequencerInbox             | `0x6327D32D966C666C750dD4058e909415F44ac831`                   |
| Inbox                      | `0x29C602aA09dfBac89e233c989Fd28ACf45a541B5`                   |
| RollupEventInbox           | `0x6EcbE0BDD8174ef2422182Eeb89F0857044111b4`                   |
| Outbox                     | `0xA3036d9Ec8D942acd976F0532cC689f1eC667111`                   |
| ERC20Bridge                | `0x58C53D54319bFCd77b6CD88EdE00c44466BDE035`                   |
| SequencerInbox (2nd)       | `0x8b95ca895fDCDA31Fe5ef40F192B181F56396898`                   |
| ERC20Inbox                 | `0xAd1fE6FE4F62006a167a25539f644485D57Ff45D`                   |
| ERC20RollupEventInbox      | `0xb4336730c7EE24B4Ca466e880277BF95Aff82B04`                   |
| ERC20Outbox                | `0x5938191577f48A6b09c802847fF2E2639763a648`                   |
| BridgeCreator              | `0xd83Eac9830b0C28248618Ed0a6098d891F18F2f0`                   |
| OneStepProver0             | `0xD5261bFc7785D82C3Cdc73816a1C6Fd42eE15970`                   |
| OneStepProverMemory        | `0xBF44cA2F235DC05bBC94a8A0e0Cd9240E4D676A2`                   |
| OneStepProverMath          | `0xafaC12DbF7be52C40a2fdE80336AE11124788eF2`                   |
| OneStepProverHostIo        | `0x6b171770E9E95279BF35966F17E8BF59Cd89c9e8`                   |
| OneStepProofEntry          | `0x82A0fE389ac95099e982bB1F04f0B028019AC40f`                   |
| ChallengeManager           | `0x39E98a358dE86114465Cd39DE945e07B1443C94F`                   |
| RollupAdminLogic           | `0xb30fC27A86Aaa9Ad8D7593b137AD4990e5e8E141`                   |
| RollupUserLogic            | `0xE099C33c50F085357A6Eb5A6Fe436ba3CD0afc06`                   |
| ValidatorUtils             | `0xdCB559e92e86d9E0a379b5A68C5500CbF7f97bef`                   |
| ValidatorWalletCreator     | `0x635BaC4ed3321ba4E8E5f5B1921C73B8ff6f7278`                   |
| RollupCreator              | `0xeBa1B57d21b691f54878ca2031b8F056Cb52dfF1`                   |
| DeployHelper               | `0x915769817Cad0Ed3EfB9744504889DF1D7c6D476`                   |
| RollupProxy                | `0x9262FfF5ac8eFDb75229C30c0baB2f29404B528A`                   |

### Rollup Creation Addresses

| Contract (Proxy)           | Address                                                        |
|----------------------------|----------------------------------------------------------------|
| RollupProxy                | `0xe95b56C40806dB07817f81Bb33231dA5558B6f44`                   |
| Inbox (proxy)              | `0x20A1CDaAfaB8F5DbDD335929e115554715C51aAb`                   |
| Outbox (proxy)             | `0x693A4718212f786D527eda65d9ce9097D677486B`                   |
| RollupEventInbox (proxy)   | `0x019d59dB566F20Fc94d9e0Bbf5596AB4eD053492`                   |
| ChallengeManager (proxy)   | `0xF64f0C5f2C0bC72B3A0A52e09d8De0c1cbC2A9B2`                   |
| AdminProxy                 | `0x8FBF7E4983E03D56DB2764151aa61Bfe14c935B3`                   |
| SequencerInbox (proxy)     | `0x7B52E238C8c2ACFb611854429AF13f47e96bF1AC`                   |
| Bridge (proxy)             | `0xd0aa1D1865878d23465fE1c4516675F9A176f81d`                   |
| ValidatorUtils             | `0xdCB559e92e86d9E0a379b5A68C5500CbF7f97bef`                   |
| ValidatorWalletCreator     | `0x635BaC4ed3321ba4E8E5f5B1921C73B8ff6f7278`                   |

**Deployment Block Number:** 138330136  
**Rollup Creation Transaction:** [View Transaction](https://sepolia.arbiscan.io/tx/0xb65ea0a5463ea7d68b92f025fd649dc1a24ea3bfd78be0c11dc06a554c35c8c8)

---

## Logs and Verification Details

### Nitro Contract Output

The **contract-output.md** file includes detailed logs showing:
- Deployment addresses.
- Verification steps with links to block explorer pages.
- Notes on contracts that were already verified or require specific parameters (e.g., the `ChallengeManager`).

### Rollup Output

The **rollup_output.md** file records:
- The creation of the rollup via the `createRollup` function.
- Addresses for the RollupProxy and associated proxy contracts.
- A summary message confirming the successful rollup creation.
- The transaction ID for rollup creation, which is linked to the block explorer.

---

## How to Use This Repository

1. **Review the Logs:**  
   - Check `contract-output.md` for contract deployment details.
   - Check `rollup_output.md` for the rollup creation process and final output.

2. **Set Environment Variables:**  
   Ensure that any required environment variables (like `ESPRESSO_LIGHT_CLIENT_ADDRESS`) are set before deployment.

3. **Verify Contracts:**  
   Follow the log instructions to verify contracts on your preferred block explorer. For contracts with multiple bytecode matches (e.g., `ChallengeManager`), use the `--contract` flag as indicated in the logs.

4. **Explore Deployed Contracts:**  
   Use the provided block explorer links to view the contract code and verification details.

---

## Conclusion

This repository offers a comprehensive record of the Nitro Rollup deployment process—from contract deployment and verification to rollup creation. Use the provided documentation and logs to review the process, debug any issues, or verify the deployed contracts on the block explorer.

Happy deploying!
