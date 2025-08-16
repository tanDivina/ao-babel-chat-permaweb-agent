# 🤖 AO Babel Chat

**A fully decentralized, real-time, multilingual chat application and translation service for the AO ecosystem.**

---

**Hackathon Submission for: [Agents of the Permaweb: The AO Autonomous Agents Hackathon](https://example.com/hackathon-link)**

-   **Track:** AI-Enhanced Applications
-   **Bonus Prizes Targeted:** AstroUSD, Apus Network, RandAO

**Live Demo:** [Link to the deployed Permaweb App - to be added]

---

### The Problem

The AO community is global, but the primary community chat is English-only. As seen in the official Discord, this creates a significant barrier for non-English speakers who must manually translate messages back and forth to participate. This friction limits global collaboration and community growth.

### The Solution: AO Babel Chat

AO Babel Chat is a censorship-resistant, serverless chat application that breaks down language barriers. Users can set their preferred language, and every message is translated in real-time for every participant.

This is made possible by a multi-agent architecture running entirely on AO:

1.  **BabelFish Agent:** A reusable, on-chain microservice that provides translation for any AO application, using the **Apus Network** for verifiable AI inference.
2.  **Chatroom Agent:** A modified version of the standard `chatroom` blueprint that orchestrates the real-time translation of all messages.
3.  **Frontend dApp:** A user-friendly interface built with React, deployed permanently on Arweave.

### ✨ Key Features

*   **Real-Time, In-App Translation:** Write in your native language, read in yours.
*   **Fully Decentralized:** No servers, no censorship, no single point of failure.
*   **Powered by On-Chain AI:** Leverages the Apus Network for secure and verifiable AI translation.
*   **Sustainable Economics:** Features a "Freemium" model with a Pro tier unlocked by **AstroUSD (USDA)**.
*   **Community Governed:** Pro users can propose and vote on corrections to improve translation quality over time.
*   **Spontaneous Connections:** Uses **RandAO** to randomly pair users for 1-on-1 language exchange sessions.

### 🚀 Getting Started

**Prerequisites:**
*   [Node.js v20+](https://nodejs.org/)
*   The `aos` CLI (`npm i -g aos`)
*   An Arweave wallet (`wallet.json`)

**Running Locally:**

1.  **Clone the repository:**

    git clone [Your Repo URL]
    cd ao-babel-chat
 

2.  **Deploy the BabelFish Agent:**
  
    aos BabelFishAgent --wallet wallet.json --load ./agents/babel-fish.lua


3.  **Deploy the Chatroom Agent:**
    
    aos BabelChatroom --wallet wallet.json --load ./agents/chatroom.lua


4.  **Run the Frontend:**
   
    cd frontend
    npm install
    npm run dev
    

### 🛠️ Technical Architecture

Our system is a demonstration of AO's composability, using a message-passing architecture between specialized agents.

1.  A user sends a message in e.g. Turkish from the frontend dApp to the **Chatroom Agent**.
2.  The Chatroom Agent forwards the text to our **BabelFish Agent**.
3.  The BabelFish Agent sends an `Infer` request to the **Apus Network Agent**.
4.  The Apus agent performs the translation and sends the result back to BabelFish.
5.  BabelFish processes the result and sends the structured, multilingual object back to the Chatroom.
6.  The Chatroom broadcasts this object to all connected users.
7.  Each user's frontend displays the translation matching their chosen language.

### 🌟 Hackathon Goals

*   **Practical Utility:** Solves a documented, immediate problem for the AO community.
*   **Technical Implementation:** Demonstrates a complex, asynchronous, multi-agent architecture.
*   **Autonomy:** Agents operate continuously and govern themselves without developer intervention.
*   **User Experience:** Provides a clean, intuitive, and powerful user interface.
*   **Innovation:** Creates the first on-chain, real-time, multilingual chat and translation service for the permaweb.
