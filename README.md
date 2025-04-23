# NERO Loop

NERO Loop is a decentralized subscription protocol built on NERO Chain designed to enable seamless, recurring payments for Web3 applications. 
By leveraging Account Abstraction, the Paymaster system, and the UserOpSDK, NERO Loop allows developers to offer gasless, multi token subscription experiences that feel as intuitive as Web2 services.

This protocol is ideal for use cases across GameFi, SocialFi, and DeFi enabling dApps to introduce monetization through recurring services, memberships and premium features without compromising on user experience.

## Project Idea 🧠

Recurring payments are foundational to digital services yet remain underdeveloped in Web3 due to the complexity of gas fees, token approvals, and wallet management. 
For users, this results in a fragmented and often frustrating experience especially for those new to blockchain technology.

NERO Loop solves this by offering a decentralized, gasless subscription protocol on NERO Chain. 
It enables dApps to provide seamless subscription based access to services, memberships and features across verticals like GameFi, SocialFi, and DeFi.

What makes NERO Loop possible is the deep integration with the NERO Chain development ecosystem:

- **Account Abstraction** enables user centric experiences by allowing dApps to manage transactions on behalf of users, abstracting away technical barriers like gas and signature complexity.
  
- **Paymaster Integration** ensures that users can subscribe to services without needing to hold NERO tokens or pay gas fees directly. Subscriptions can be sponsored, discounted, or processed in ERC-20 tokens of the user’s choice.
  
- **UserOpSDK** is the core development tool behind NERO Loop. It simplifies the creation, signing and transmission of UserOperations, allowing for:

  -> Creation of smart contract wallets during onboarding
  -> Automated scheduling of recurring transactions
  -> Seamless communication with bundlers
  -> Token agnostic gas fee management

By combining these tools, NERO Loop creates a Web3 subscription engine that functions as easily as a Web2 payment gateway allowing dApp developers to onboard users at scale without compromising on decentralization, user control, or security.

---

## How It Works💡

NERO Loop enables decentralized, gasless subscription payments by integrating NERO Chain’s Account Abstraction features and the UserOpSDK. The system abstracts away the traditional Web3 complexity like gas fees and wallet management while maintaining full decentralization and transparency.

### 1. User Onboarding

When a user accesses a NERO Loop enabled dApp:

- They are offered to sign up using a social login (email or wallet).
- A smart contract wallet is created onchain using the **UserOpSDK**.
- The wallet is linked to their identity and capable of executing automated subscription transactions.

This wallet setup process is fully abstracted from the user, offering a near Web2 like onboarding experience.

---

### 2. Subscription Setup

To initiate a subscription:

- The user selects a subscription plan (e.g., monthly, quarterly).
- The dApp triggers a **UserOperation** via the SDK to define:
  - The payment interval
  - The amount and token to be charged
  - The recipient address (merchant or dApp admin)
- The operation is signed and submitted to a **bundler**.
- A **Paymaster** sponsors the gas cost or deducts it from an approved ERC-20 token.

This creates an automated, renewable transaction that executes on schedule without requiring further user action.

---

### 3. Automated Renewals

At the scheduled interval:

- The dApp or backend triggers a new **UserOperation** that:
  - Verifies subscription status and balance
  - Executes the token transfer from the user’s smart contract wallet
  - Updates subscription state
- The transaction is relayed to the bundler
- The Paymaster handles the gas payment logic

If the user has insufficient funds or cancels, the smart contract logic halts the subscription and notifies the dApp.

---

### 4. Developer Integration

For developers, integration is simple using NERO Loop’s SDK layer:

- Install the **UserOpSDK** to manage wallet operations, transaction creation, and communication with the bundler.
- Use the provided hooks and APIs to:
  - Initiate wallet creation
  - Configure custom subscription plans
  - Monitor payment success and failures
  - Offer multi token payment choices
- Connect to NERO's Paymaster APIs to configure gas sponsorship or discounts.

---

### 5. Admin Dashboard (Planned)

A no code dashboard is in development to allow dApp admins to:

- View active subscribers and revenue
- Set plan pricing and renewal intervals
- Configure token based Paymaster rules
- Export onchain audit data for compliance and analytics

---

### End to End Flow Summary

1. **User signs up →** Smart contract wallet is created
2. **User selects a plan →** Subscription operation is created and signed
3. **Transaction submitted →** Bundler and Paymaster handle execution
4. **Renewal cycles →** Automatic transactions continue without user involvement
5. **Admin panel →** Track and manage subscription business

---

## Unique Selling Points✅

NERO Loop stands out as a Web3 native subscription infrastructure by solving critical pain points for both users and developers. 
Here’s what makes it unique:

### 1. Gasless, Seamless Subscriptions
Users can activate and maintain subscriptions without ever managing gas fees. Paymasters handle gas costs automatically or allow payments in familiar ERC-20 tokens, enabling a Web2 like experience.

### 2. One Time Authorization
A single signature at the start creates a smart wallet and configures future payments. 
No repeated confirmations or approvals are needed, reducing user drop off and making renewals frictionless.

### 3. Built on NERO Chain’s AA Stack
NERO Loop uses native tools like **UserOpSDK** and **Paymasters**, showcasing the full potential of Account Abstraction in production. 
It's not just a demo, it’s a real world implementation of NERO’s core innovations.

### 4. Token Agnostic Billing
Supports any ERC-20 token as a payment method. 
Projects can configure loyalty tokens, stablecoins or native assets for user payments flexible enough to match any economic model.

### 5. Real Revenue for dApps
Unlike many hackathon concepts, NERO Loop introduces a clear monetization path: recurring income from users for access, features, or memberships sustainability built in.
---


## Example Use Cases

### 1. GameFi: Premium Access Pass
A blockchain based game offers a "Pro Battle Pass" for competitive players. Users can subscribe monthly using their preferred ERC-20 token, gaining access to exclusive tournaments, loot boxes, and cosmetic upgrades. All transactions are gasless and automatically renewed each month.

### 2. DAO Services: Operational Contributions
A DAO manages contributor compensation through NERO Loop, setting up automated token based "stipend" subscriptions for recurring contributors. 
This ensures timely, auditable payments without requiring manual interaction or high gas costs.

### 3. NFT Utility Subscriptions
A project can tie NFT ownership to an active subscription using NERO Loop. The NFT acts as a membership token, while behind the scenes, the subscription contract manages access and renewals. 
Users can transfer the NFT, and the subscription logic resets or pauses automatically.

---

## Tech Stack

• **Frontend**: React.js, TailwindCSS, WalletConnect / Web3Modal
• **Backend**: Bundler API (NERO Docs), Node.js / TypeScript, 
• **Blockchain**: NERO Chain & ERC-4337, UserOpSDK, Paymaster System
• **Smart Contracts**: Solidity, Hardhat, OpenZeppelin

