# Neo Tutorial : Understanding and Utilizing Neo Technologies

Welcome to the **Neo Tutorial Series**, your ultimate guide to exploring the functionalities, features, and applications of Neo. This tutorial aims to empower you with the knowledge and tools to confidently build on Neo, whether you're a beginner or an experienced developer.

---

## **Table of Contents**
1. [Introduction to Neo Ecosystem](#1-introduction-to-neo-ecosystem)
2. [Setting Up the Development Environment](#2-setting-up-the-development-environment)
3. [Writing and Deploying Your First Smart Contract](#3-writing-and-deploying-your-first-smart-contract)
4. [Integrating Oracles: Using Supra Oracle on Neo](#4-integrating-oracles-using-supra-oracle-on-neo)


## **1. Introduction to Neo Ecosystem**
Neo is a blockchain platform designed for creating decentralized applications (dApps). It aims to establish a smart economy by integrating digital assets, digital identity, and smart contracts.

### Key Features of Neo:
1. **NeoVM**: A lightweight virtual machine for executing smart contracts efficiently.  
2. **NeoID**: A decentralized identity solution for managing digital identities.  
3. **NeoFS**: A distributed file storage system for decentralized applications.  
4. **Dual-Token Model**: NEO (governance) and GAS (transaction fees).  

### Why Choose Neo?
- High throughput and low transaction costs.  
- Native integration with oracles, file storage, and identity systems.  
- Developer-friendly tooling and multi-language support.  

Learn more at [Neo.org](https://neo.org).


## **2. Setting Up the Development Environment**

### Step 1: Install Neo-CLI  
Neo-CLI is the command-line tool for interacting with the Neo blockchain.

#### Installation:  
1. Download Neo-CLI from the [Neo GitHub releases](https://github.com/neo-project/neo-node/releases).  
2. Extract the files and navigate to the directory in your terminal.  
3. Run Neo-CLI:  
   ```bash
   dotnet neo-cli.dll
   ```

### Step 2: Install Neo Express  
Neo Express is a local blockchain emulator for testing.

#### Installation:  
1. Install via npm:  
   ```bash
   npm install -g neo-express
   ```
2. Create a new local blockchain:  
   ```bash
   neo-express create -n TestNet
   ```

### Step 3: Set Up IDE (Visual Studio Code)  
1. Install Visual Studio Code.  
2. Add the [Neo Blockchain Toolkit](https://marketplace.visualstudio.com/items?itemName=ngd-seattle.neo-blockchain-toolkit) extension, NEXT.

### Step 4: (Optional) Configure Termux for Android  
1. Install Termux from the [F-Droid repository](https://f-droid.org/en/packages/com.termux/).  
2. Install Node.js and Neo Express:  
   ```bash
   pkg install nodejs
   npm install -g neo-express
   ```


## **3. Writing and Deploying Your First Smart Contract**

### Goal is to:
Write and deploy a "Hello, Neo!" smart contract using Python.

### Writing the Contract:
1. Create a file named `hello_neo.py`:  
   ```python
   from boa3.builtin import public

   @public
   def main() -> str:
       return "Hello, Neo!"
   ```

2. Save the file in your project folder.

### Compiling the Contract:
1. Install Boa Python compiler:  
   ```bash
   pip install boa3
   ```
2. Compile the contract:  
   ```bash
   boa hello_neo.py
   ```

### Deploying the Contract:
1. Start Neo Express:  
   ```bash
   neo-express run
   ```
2. Deploy the contract using the `deploy` command, as seen below:  
   ```bash
   neo-express deploy hello_neo.nef
   ```

### Testing:
1. Invoke the contract:  
   ```bash
   neo-express invoke HelloNeo.main
   ```
2. You should see the output like this: `Hello, Neo!`.



## **4. Integrating Oracles: Using Supra Oracle on Neo**

### Overview:
Oracles allow smart contracts to access real-world data. Supra Oracle is a service that integrates seamlessly with Neo.

### Writing a Contract to Fetch Data:
1. Create a file `oracle_example.py`:  
   ```python
   from boa3.builtin.interop.oracle import Oracle
   from boa3.builtin import public

   @public
   def get_weather(api_url: str) -> str:
       return Oracle.request(api_url)
   ```

2. Replace `api_url` with a real-world API endpoint.

### Testing Oracle Integration:
1. Deploy the contract using Neo Express.  
2. Call the `get_weather` function with the desired URL.  



Thanks for your time

-

I think I will stop here for today,together, let's make Neo technology accessible to everyone!

