# MyToken (MTK)

## Overview
MyToken is a simple ERC-20 token built on the Ethereum blockchain for learning and experimentation. It includes all standard ERC-20 functions such as transfers, allowances, and event logging. This project demonstrates how tokens work behind the scenes.

---

## Token Details
- **Name:** MyToken
- **Symbol:** MTK
- **Decimals:** 18
- **Total Supply:** 1,000,000 MTK
- **Contract Address:** `0x406AB5033423Dcb6391Ac9eEEad73294FA82Cfbc`

**Addresses used in examples:**
- **Owner:** `0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2`
- **Spender / Recipient:** `0x5B38Da6a701c568545dCfcB03FcB875f56beddC4`

---

## What is ERC-20?
ERC-20 is the official token standard used to create fungible tokens on Ethereum.  
It defines a consistent set of functions and events such as:

- `transfer`
- `approve`
- `allowance`
- `balanceOf`
- `transferFrom`
- `Transfer` and `Approval` events

Because all ERC-20 tokens follow this interface, wallets and exchanges can interact with them easily.

---

## Features
- ✅ Standard ERC-20 Token Implementation  
- ✅ Transfer Between Addresses  
- ✅ Allowances & Third-Party Spending (transferFrom)  
- ✅ Emits Transfer & Approval Events  
- ✅ Zero-Address & Balance-Check Safeguards  

---

## Deployment Instructions (Remix IDE)

1. Visit **https://remix.ethereum.org/**
2. Create a new file named **MyToken.sol**
3. Paste your contract code
4. Compile using **Solidity v0.8.x**
5. Open **Deploy & Run Transactions**
6. Enter initial supply:
   ```
   1000000 * 10^18
   ```
7. Click **Deploy**
8. Copy and save your contract address

---

## Usage Examples  

### 🔹 Check Balance (Owner)
```solidity
balanceOf("0x5B38Da6a701c568545dCfcB03FcB875f56beddC4")
```

---

### 🔹 Transfer Tokens (Owner → Recipient)
Send 100 MTK from Owner to Spender/Recipient:
```solidity
transfer("0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2", 100 * 10**18)
```

---

### 🔹 Approve Spender (Owner approves Spender)
Owner allows Spender to spend 500 MTK:
```solidity
approve("0x5B38Da6a701c568545dCfcB03FcB875f56beddC4", 500 * 10**18)
```

---

### 🔹 Check Allowance (Owner → Spender)
```solidity
allowance(
    "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
    "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4"
)
```

---

### 🔹 Transfer Using Allowance (transferFrom by Spender)
Spender transfers tokens from Owner to Spender using allowance:
```solidity
transferFrom(
    "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",  // owner
    "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",  // recipient
    200 * 10**18
)
```

---

### 🔹 Check Total Supply
```solidity
totalSupply()
```

---

## Testing Scenarios & Results

| Test Case | Description | Expected Outcome | Result |
|----------|-------------|------------------|--------|
| Transfer tokens | Owner → Recipient (100 MTK) | Balance increases | ✅ Passed |
| Approve allowance | Owner approves Spender | Allowance stored | ✅ Passed |
| transferFrom | Spender spends 200 MTK | Balances update | ✅ Passed |
| Insufficient balance | Transfer > balance | Should revert | ✅ Passed |
| Zero address test | Transfer to 0x0 | Should revert | ✅ Passed |
| totalSupply() | Returns full supply | 1,000,000 MTK | ✅ Passed |

---

## What I Learned
- How ERC-20 standards define token behavior  
- How allowances and transferFrom work for decentralized applications  
- How to deploy and test contracts using Remix  
- How events track token movement  
- Importance of validating zero address  
- How to safely manage token supply and balances  

---
