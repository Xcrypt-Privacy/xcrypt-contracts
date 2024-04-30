# Xcrypt

Xcrypt is a non-custodial solution that uses stealth addresses which enables users to receive funds on Scroll Blockchain without revealing receivers real address.

## 📝 Project Description

### ✍ Project Overview
- Xcrypt is a privacy-focused solution addressing the need for anonymity in blockchain transactions. It tackles the risk of exposing the identities and financial information of users by enabling anonymous transactions on the Scroll Blockchain. The solution utilizes stealth addresses on the Scroll Blockchain, allowing users to receive funds without revealing their real addresses.
- The project draws inspiration from existing privacy-focused blockchains like Monero and tools like Tornado Cash, but aims to bridge the gap between complex and expensive privacy solutions and non-private transfers.
- It empowers users to maintain their privacy, fostering trust and security in the blockchain industry.
- Overall, Xcrypt has the potential to become a leading privacy solution, ensuring the confidentiality and anonymity of blockchain transactions.

### 😎 Idea
- I've always been fascinated by the concept of anonymity in blockchains, with various methods available to achieve it.
- Privacy-focused blockchains like Monero and widely-used networks like Tornado Cash, which is based on anonymity sets or zero-knowledge proof solutions, provide near-perfect privacy for both parties in a transaction.
- However, they require specialized tools or come at a higher cost than direct transfers, leaving a gap between expensive, complex solutions and non-private transfers.
- Recently, Vitalik published an article titled "An Incomplete Guide to Stealth Addresses," which provided missing pieces of a simple yet effective solution for anonymous transactions, at least for the receiving party.
- Inspired by this idea we decided to create a user-friendly tool utilizing stealth addresses. We chose Scroll as the initial network for its implementation due to its fast and affordable transactions.

### ⚔ What’s difference between Xcrypt and other wallets?
Xcrypt is all about keeping your financial matters private. Unlike regular wallets, where sharing your address can reveal what you've been up to, Xcrypt is different. Instead of giving out your real wallet address, you share something called a Xcrypt ID. It's like a secret code, and it doesn't link to any specific place on the blockchain.

When you want someone to send you money, Xcrypt uses a special method called Diffie-Hellman key exchange (don't worry, we won't get too technical). The result is a new secret address created just for that transaction. The cool part is, even the person sending you money can't figure out your real wallet address because you only share your Xcrypt ID with them. And each time, a fresh new address is made.

Only you, the owner of the Xcrypt ID, have control over these secret addresses. Everyone else, including the sender, doesn't know where your real wallet is—it's like a constantly changing secret. Xcrypt makes privacy easy and clever, so your financial business stays your business.

### 📺 Background & Context
- Issue Addressed: Xcrypt addresses the pressing concern of inadequate privacy in blockchain transactions. While the blockchain guarantees transparency and immutability, it simultaneously exposes sensitive details of transactions, such as sender and recipient addresses. This lack of privacy imposes significant risks on both individuals and businesses, potentially connecting their financial actions to real-world identities.

- Fundamental Privacy: Privacy holds a crucial role in financial transactions. Without a robust privacy layer, users remain vulnerable to an array of risks:

    - Identity Exposure: Open blockchain transactions create an avenue for observers to correlate transactions with specific people or entities. This jeopardizes financial privacy and exposes individuals to potential targeting or surveillance.

    - Financial Profiling: In-depth profiling of individuals and businesses becomes possible through the analysis of blockchain transactions. This includes identifying spending habits, income sources, and financial associations. Such data can be exploited for targeted ads, discrimination, or even extortion.

    - Security Gaps: Transparent blockchains, when repeatedly used for transactions, render users susceptible to hacking and phishing threats. Criminals can analyze transaction histories to discern patterns, monitor balances, and exploit security vulnerabilities.

    - Business Exposure: Transparent transactions inadvertently reveal confidential financial information of companies, like sales figures, supply chain connections, and partnerships. Competitors can leverage this intel to gain an edge, potentially undermining business competitiveness.

    - Regulatory Hurdles: Certain industries, such as healthcare and finance, mandate stringent privacy regulations. Transparent blockchain transactions could clash with these standards, resulting in legal complications or penalties for non-compliance.

- Significance: Addressing this issue assumes paramount importance due to its direct impact on safeguarding financial confidentiality. Preserving the integrity of personal and corporate information from prying eyes is central. By introducing a user-centric solution that leverages stealth addresses for anonymous transactions, Xcrypt empowers users to regain control over their financial privacy and alleviate the potential pitfalls linked with identity exposure.

### ☄️ Value Proposition
- Enhanced Privacy: Xcrypt utilizes stealth addresses, allowing users to receive funds without revealing their real addresses. This provides a significant level of privacy for individuals and businesses, ensuring that their financial activities are shielded from prying eyes.

- User-Friendly Solution: Xcrypt aims to be accessible and user-friendly for both power users and non-power users. The generation and usage of Xcrypt IDs and stealth addresses are designed to be simple and intuitive, enabling a wide range of users to adopt and utilize the solution without technical complexity.

- Affordability and Speed: Xcrypt is built on the Scroll Blockchain, chosen for its fast and affordable transactions. By leveraging Scroll blockchain, Xcrypt offers users the benefits of privacy without sacrificing transaction speed or incurring high fees commonly associated with other privacy-focused solutions.

- Bridge the Gap: Xcrypt fills the gap between expensive and complex privacy solutions, such as Monero, and non-private transfers on transparent blockchains. It provides an intermediate solution that offers a significant level of privacy without the need for specialized tools or high costs.

- Wide Applicability: Xcrypt's privacy solution can be applied to various use cases. It can benefit individuals who want to keep their financial transactions private, businesses that need to protect their financial information, and anyone concerned about the risks associated with revealing their identity during transactions.

- Market Differentiation: Xcrypt stands out in the market by offering a unique approach to privacy in blockchain transactions. While other solutions rely on heavy computations or complex methodologies, Xcrypt simplifies the process with stealth addresses and Xcrypt IDs, making it more accessible and user-friendly.

### ✒ Technical Description
- The Xcrypt solution implements stealth addresses on the Scroll Blockchain using a combination of cryptographic techniques to ensure transaction security and user privacy. Let’s break down the key steps and encryption methods involved:

- Stealth Addresses Generation:
    Receiver, generates a root spending key (receiver private key) and computes a stealth meta-address (receiver public key or receiver’s address) using elliptic curve cryptography. This stealth meta-address (receiver’s address) becomes a publicly known identifier for the receiver on the blockchain.

- Ephemeral Key Generation:
    The Sender, generates an ephemeral key (sender’s private key) which the sender keeps secret. This key is like a temporary secret code.

- Shared Secret Creation:
    The Sender combines his ephemeral key (sender’s private key) with Receiver’s stealth meta-address (receivers public key) to create a shared secret (S). This shared secret is a private connection between Sender and Receiver.

- Ephemeral Public Key Publishing:
    Sender creates an ephemeral public key (senders public key) from his ephemeral key (senders private key) and publishes it on a public registry. This public key can be seen by anyone.

- Transaction Process:
    Sender sends funds to a stealth address, which is derived from the combination of his ephemeral key (senders private key) and Receiver’s meta-address (receivers public key).

- Recipient’s Discovery:
    Receiver scans the public registry for ephemeral public keys (senders public key) and tries to unlock special addresses (stealth addresses) using his spending key (receivers private key) and the shared secrets (S). If funds are found in an address, Receiver can access them.

- Address Ownership and Privacy:
    The transaction details are recorded on the blockchain, but the connection between the recipient’s real address and the stealth address remains private. This adds a layer of privacy by making it difficult for external observers to link transactions to specific recipients.

- The cryptographic techniques used in this process include:

    Elliptic Curve Cryptography (ECC): This is used to generate private and public keys, compute shared secrets, and create addresses. ECC provides a secure way to perform mathematical operations that ensure transaction security and privacy.

    Hash Functions: Hashing is used to derive addresses from public keys and shared secrets. Hash functions are one-way functions that add an extra layer of security to the process.

    Public Key Registries: The public registry where ephemeral public keys are published allows participants (like Receiver) to scan and identify stealth addresses. This mechanism helps maintain privacy without revealing the actual recipient’s address.

The Xcrypt solution leverages these cryptographic methods to create a system where transactions are secure, and recipient privacy is preserved through the use of stealth addresses.

### 💻 Implementation
- We have started with a standard Hardhat project and added essential methods to the StealthAddress contract. To enhance credibility, we intentionally avoided making the contract upgradeable, as there's no on-chain governance currently. If an upgrade is needed, we'll deploy a new version and provide client-side support.
- Next, we developed the UI/UX using React and TypeScript, focusing on a simple yet elegant design for both power and non-power users. The UI colors and feel is being build keeping in mind the Scroll Blockchain.
- We used wagmi library for blockchain interactions which streamlined the process.
- The elliptic library handled the complex math involved with elliptic curves, and both libraries featured TypeScript typings, making them a joy to work with.
- Tools Used: Solidity, Hardhat, Scroll Blockchain, React, Typescript, Wagmi and Metamask.

### 👥 Intended Users
- The intended users of Xcrypt would be anyone who values privacy in their transactions and wants to keep their identity hidden. This could include individuals who want to keep their financial transactions private, businesses that want to protect their financial information, or anyone who wants to avoid the risks associated with revealing their identity in a transaction.
- Xcrypt is designed to be user-friendly for both power and non-power users, making it accessible to a wide range of people.

### ⚔ Challenges
- The main challenge was designing the best possible user experience, which we believe the current implementation achieves.
- Another challenge was signing and sending withdrawal transactions without using the connected user wallet. We resolved this by creating a custom-built transaction broadcasted via public RPC URLs, which works effectively.

### Acknowledgements
- The project is being inspired from Umbra Protocol and Hazed and some parts of the code has been used.
- The deployment on the Scroll Blockchain and its integration with the Scroll Blockchain is our original work.
- Also the transferring of 1% of the total amount as platform fees is something that have been done for the first time.

### Previous Works
- Xcrypt has been sumbitted to BNB Hackathon and XRPL Hackathon.

### 💹 Market Analysis
- Xcrypt's solution addresses a significant market opportunity by providing privacy in blockchain transactions. Privacy has become a crucial concern in the blockchain industry as individuals and businesses increasingly recognize the risks associated with transparent transactions. By offering a user-friendly and accessible solution, Xcrypt taps into a growing demand for privacy-enhancing tools in the blockchain space.
- The Total Addressable Market (TAM) for Xcrypt's solution is substantial. As blockchain technology continues to gain adoption across industries, the need for privacy in transactions becomes more prevalent. Individuals who value financial privacy, businesses seeking to protect sensitive financial information, and anyone concerned about the risks of identity exposure in transactions represent a wide range of potential users for Xcrypt.
- Xcrypt differentiates itself from incumbent competitors by providing a simpler and more cost-effective solution. Existing privacy-focused blockchains like Monero require specialized tools and incur higher costs, making them less accessible to mainstream users. Xcrypt bridges the gap between complex and expensive privacy solutions and non-private transfers, offering a user-friendly option with its stealth address implementation. The ease of generating Xcrypt IDs and utilizing stealth addresses sets Xcrypt apart from incumbent competitors.
- Furthermore, Xcrypt leverages the Scroll Blockchain, which provides fast and affordable transactions. This strategic choice enhances the scalability and usability of the solution, making it attractive to users who prioritize transaction speed and cost-efficiency.

### ☄️ What's next?
- Currently, Xcrypt only supports native coin transfers(ETH). However, adding support for tokens and NFTs would greatly enhance its utility. We are considering implementing relayer nodes to mint and sell notes as tokens (or NFTs) in exchange for covering user fees on transfers.
- This approach allows users to maintain their anonymity while using note tokens to request relayers to cover fees and pay for transactions. Competition between relayers could help keep transfer fees reasonable.
- Deploying Xcrypt on the Scroll Mainnet as soon as possible 😉.
- Expanding Xcrypt by enabling cross-chain transactions. Additionally, gas optimization in the StealthAddress contract and its interaction with the receiving side can be improved.
- Obtaining a legal opinion on Xcrypt's regulatory compliance would be beneficial. However, since the StealthAddress contract is on the blockchain and the code is available on GitHub, funds will remain accessible even if the website is shut down.
- Future UX improvements include notifications for funds received on new controlled stealth addresses and a mobile app (although the website is mobile-friendly). The possibilities are endless!

### 🌟 Conclusion
- Xcrypt is a user-friendly and innovative solution that addresses the growing need for privacy in blockchain transactions. By leveraging stealth addresses and the Scroll Blockchain, Xcrypt provides a simple and cost-effective way for users to keep their financial transactions private. With a substantial market opportunity and a focus on usability, Xcrypt has the potential to become a leading privacy solution in the blockchain industry.

### 💪 Deployed Contract Addresses (Scroll Testnet)
- StealthAddress Contract: [0x2a80F477AC918Ed4daA44112a0108E4185dfC6BD](https://sepolia.scrollscan.com/address/0x2a80F477AC918Ed4daA44112a0108E4185dfC6BD#code)
