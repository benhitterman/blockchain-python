# Simple Blockchain in Python

A basic, functional blockchain implementation in Python.

## 🚀 Features

- Build and manage a blockchain from scratch in Python
- Add transactions and mine blocks with proof-of-work
- Register and connect multiple nodes
- Achieve consensus across nodes (longest valid chain wins)
- Run multiple Flask servers locally to simulate a decentralized network

## 🛠 How to Run

### 1. Clone and set up

```bash
git clone https://github.com/YOUR_USERNAME/blockchain-python.git
cd blockchain-python
python3 -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
```

### 2. Start nodes on different ports

```bash
# Terminal 1
python blockchain.py 5001

# Terminal 2
python blockchain.py 5002
```

### 3. Interact using Postman

#### ➕ Add a transaction

POST http://localhost:5001/transactions/new  
Body (JSON):<br />

```json
{
  "sender": "address_1",
  "recipient": "address_2",
  "amount": 10
}
```

#### ⛏️ Mine a block

GET http://localhost:5002/mine

#### 🔗 Register another node

POST http://localhost:5001/nodes/register  
Body (JSON):

```json
{
  "nodes": ["http://localhost:5002"]
}
```

#### 🔄 Resolve chain with consensus

GET http://localhost:5001/nodes/resolve

#### 🧾 View the blockchain

GET http://localhost:5001/chain

## 📬 API Endpoints

| Method | Endpoint            | Description                 |
| ------ | ------------------- | --------------------------- |
| GET    | `/chain`            | View the current blockchain |
| POST   | `/transactions/new` | Add a new transaction       |
| GET    | `/mine`             | Mine a new block            |
| POST   | `/nodes/register`   | Register other nodes        |
| GET    | `/nodes/resolve`    | Run the consensus algorithm |
