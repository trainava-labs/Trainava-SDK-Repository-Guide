# Trainava SDK Repository Guide

Welcome to the official **Trainava SDK Repository**. This guide provides everything developers and contributors need to understand the structure, purpose, and setup of the SDK used in the Trainava ecosystem. This SDK is the backbone that powers interactions with Trainava's decentralized GPU network, AI training infrastructure, and Telegram bot deployment tools.

> **Note**: This guide does not contain the full application code, but documents the design and usage of the SDK and developer tools used within Trainava.

---

## 📦 Repository Overview

### Folder Structure

```
trainava-sdk/
├── docs/               # Documentation & guides
├── examples/           # Example scripts and notebooks
├── src/                # SDK source code
│   ├── api/            # API clients (REST, GraphQL, Supabase)
│   ├── core/           # Core logic for training, GPU usage, bot deployment
│   ├── models/         # Interfaces and type definitions
│   ├── utils/          # Helper functions
├── test/               # Unit and integration tests
├── package.json        # NPM package config (JavaScript version)
├── README.md           # Main entry readme
└── .env.example        # Environment variable example
```

---

## 🚀 Getting Started

### Prerequisites

* Node.js (>=18.x) or Python (>=3.10) depending on the SDK version.
* A Web3 wallet (MetaMask or WalletConnect).
* Access to Trainava account and test API key.
* Supabase project credentials (if working locally).

### Installation (JavaScript version)

```bash
npm install trainava-sdk
```

### Installation (Python version)

```bash
pip install trainava-sdk
```

---

## 🔑 Authentication & API Access

### Wallet Authentication

Use wallet signature to authenticate:

```js
import { authenticateWithWallet } from 'trainava-sdk/auth';
const token = await authenticateWithWallet(walletProvider);
```

### Supabase Session

```js
import { createClient } from '@supabase/supabase-js';
const supabase = createClient(SUPABASE_URL, SUPABASE_KEY);
```

---

## 🔧 SDK Features

### 1. GPU Power Management

* **Rent GPU**: Connect and reserve GPU for training.
* **Share GPU**: Register and share local/remote GPU.

```js
import { rentGPU, listAvailableGPUs } from 'trainava-sdk/gpu';

const gpus = await listAvailableGPUs();
const session = await rentGPU(gpus[0].id);
```

### 2. AI Training Pipeline

* Train text, image, voice, or video models.
* Track real-time status via Supabase functions.

```js
import { trainModel } from 'trainava-sdk/training';

await trainModel({
  type: 'text',
  dataset: 'my-dataset.csv',
  config: {...},
});
```

### 3. Telegram Bot Deployment

* Use prebuilt templates to deploy models as bots.

```js
import { deployTelegramBot } from 'trainava-sdk/telegram';

await deployTelegramBot({
  modelId: 'xyz123',
  token: 'your_botfather_token'
});
```

### 4. Token & Payments (\$TRVN)

* Use and track \$TRVN for GPU time, training, and staking.

```js
import { checkBalance, sendTRVN } from 'trainava-sdk/token';
```

---

## 🧪 Testing

```bash
npm run test      # JavaScript
pytest            # Python
```

---

## 📚 Documentation

All docs are in the `/docs` folder or viewable at [docs.trainava.ai](https://docs.trainava.ai)

---

## 💡 Contribution Guidelines

* Fork and clone the repo.
* Use `dev` branch for new features.
* Submit a pull request with detailed explanation.

---

## 📬 Contact & Support

* Website: [https://trainava.ai](https://trainava.ai)
* Support Email: [support@trainava.ai](mailto:support@trainava.ai)
* Twitter: [@trainava\_ai](https://twitter.com/trainava_ai)
* Telegram Community: [t.me/trainava](https://t.me/trainava)

---

## 📄 License

This SDK is open-source under the **MIT License**.

---

> "Trainava isn’t just an idea—we build real tools. This SDK proves it."

Let’s make AI useful. Together.
