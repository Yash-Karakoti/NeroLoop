# NERO Loop

NERO Loop is a decentralized subscription protocol built on NERO Chain designed to enable seamless, recurring payments for Web3 applications. 
By leveraging Account Abstraction, the Paymaster system, and the UserOpSDK, NERO Loop allows developers to offer gasless, multi token subscription experiences that feel as intuitive as Web2 services.

This protocol is ideal for use cases across GameFi, SocialFi, and DeFi enabling dApps to introduce monetization through recurring services, memberships and premium features without compromising on user experience.

## Project Idea

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

This project demonstrates how powerful, developer friendly tools from NERO Chain can enable real world, revenue generating business models while delivering the smooth experience modern users expect.


## How It Works

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

This architecture ensures a frictionless experience for users while giving developers the tools to build sustainable, revenue generating dApps on NERO Chain.
---

