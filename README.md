# Polymarket Edge Engine

A local automation layer for Polymarket, built on top of OctoBot. Execute strategies from your own machine with full key custody.

---

## Overview

Polymarket Edge Engine extends OctoBot to automate trading on Polymarket. Unlike hosted solutions, everything runs locally. Your credentials and signing keys remain on your hardware at all times.

---

## Current Status

| Feature | Availability | Description |
|---------|--------------|-------------|
| Copy trading | In progress | Follow positions from Polymarket leaderboard profiles |
| Arbitrage | In progress | Identify markets where combined costs fall below 1 |
| Kalshi integration | Roadmap | Community interest tracked in project issues |
| Web UI, Telegram, paper mode | Ready | Run and test strategies without real funds |

---

## Design Principles

**Local-first architecture**

Trading bots that run on remote servers require you to hand over API credentials. A breach of that server is a breach of your account.

This project is built so execution happens on your device. Signing keys never leave your machine. The architecture makes it impossible for the developers or any third party to access your Polymarket account.

**Paper trading recommended**

Before deploying automation with real capital, use paper mode to:

- Validate strategy logic and parameters
- Compare different configurations
- Monitor behavior over time

---

## Getting Started

### Standalone executable

Pre-built binaries for Windows, macOS, Linux, and Raspberry Pi are available on the releases page.

### Docker

```sh
docker run -itd --name Polymarket-Edge-Engine -p 80:5001 \
  -v $(pwd)/user:/octobot/user \
  -v $(pwd)/tentacles:/octobot/tentacles \
  -v $(pwd)/logs:/octobot/logs \
  drakkarsoftware/octobot:predictionmarket-stable
```

Use the `predictionmarket` tag from Docker Hub.

### From source

```sh
git clone https://github.com/Drakkar-Software/OctoBot-prediction-market
cd OctoBot-prediction-market
python -m pip install -Ur requirements.txt
python start.py
```

**Requirements:** 1 CPU core at 1 GHz or higher, 250 MB RAM, 1 GB disk space.

---

## Contributing

Contributions to code and documentation are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Disclaimer

This software is provided without warranty. Do not risk capital you cannot afford to lose. The authors and contributors are not responsible for any trading losses. Begin with paper trading, review the source code, and make informed decisions about real-money usage.

---

## License

GNU General Public License v3.0 or later. See [LICENSE](https://github.com/Drakkar-Software/OctoBot/blob/master/LICENSE).

---

**Do not run this project.**
