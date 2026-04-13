# Azure Token Cost Calculator

An interactive, single-page HTML calculator that estimates token costs across **Azure OpenAI** and **Azure AI Foundry** models. Adjust total tokens, input/cached/output split, model mix, deployment tier, region, and currency to compare costs at a glance.

![Azure Token Cost Calculator](https://img.shields.io/badge/Azure-Token%20Cost%20Calculator-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)

## ✨ Features

- **23 Azure AI Models** — GPT-5.x, GPT-4.1, GPT-4o, o3/o4-mini reasoning models, plus third-party models (DeepSeek, Llama, Mistral, Phi)
- **Deployment Tier Toggle** — Switch between Global, Data Zone, and Regional pricing with availability indicators
- **26 Azure Regions** — Select your deployment region (defaults to Australia East)
- **16 Currencies** — Auto-converts from USD base pricing (AUD, EUR, GBP, JPY, INR, and more)
- **Token Split Slider** — 3-way slider to adjust Input / Cached / Output token ratios
- **Model Distribution** — Per-model percentage sliders that always sum to 100%
- **Bar Chart Visualization** — Cost breakdown per model, color-coded by provider group
- **Add/Remove Models** — Grouped dropdown to customize your model mix
- **Responsive Design** — Works on desktop and mobile

## 🚀 Quick Start

Just open `index.html` in any modern browser — no build tools, no dependencies, no server required.

```bash
# Clone and open
git clone https://github.com/element824/TokenCostInAzure.git
cd TokenCostInAzure
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

Or simply download `index.html` and double-click it.

## 📊 Included Models

### Azure OpenAI
| Model | Input/1M | Cached/1M | Output/1M |
|-------|----------|-----------|-----------|
| GPT-5.4 | $2.50 | $0.25 | $15.00 |
| GPT-5 | $1.25 | $0.125 | $10.00 |
| GPT-5 Mini | $0.25 | $0.025 | $2.00 |
| GPT-5 Nano | $0.05 | $0.005 | $0.40 |
| GPT-4.1 | $2.00 | $0.50 | $8.00 |
| GPT-4.1 Mini | $0.40 | $0.10 | $1.60 |
| GPT-4.1 Nano | $0.10 | $0.025 | $0.40 |
| GPT-4o | $2.50 | $1.25 | $10.00 |
| GPT-4o Mini | $0.15 | $0.075 | $0.60 |

### Azure OpenAI (Reasoning)
| Model | Input/1M | Cached/1M | Output/1M |
|-------|----------|-----------|-----------|
| o3 | $2.00 | $0.50 | $8.00 |
| o4-mini | $1.10 | $0.275 | $4.40 |
| o3-mini | $1.10 | $0.55 | $4.40 |
| o1 | $15.00 | $7.50 | $60.00 |

### Azure AI Foundry (Third-Party)
| Model | Input/1M | Cached/1M | Output/1M |
|-------|----------|-----------|-----------|
| DeepSeek V3.2 | $0.27 | $0.027 | $1.10 |
| DeepSeek R1 | $0.55 | $0.14 | $2.19 |
| Llama 3.1 8B | $0.02 | $0.02 | $0.05 |
| Mistral Small 3.1 | $0.10 | $0.10 | $0.30 |
| Phi-4 Mini | $0.22 | $0.22 | $0.22 |

> Prices shown are USD Global Standard (pay-as-you-go). Always check the official [Azure OpenAI Pricing](https://azure.microsoft.com/en-us/pricing/details/azure-openai/) and [AI Foundry Pricing](https://azure.microsoft.com/en-us/pricing/details/ai-foundry-models/aoai/) pages for current rates.

## 🛠 How It Works

The calculator is a single self-contained HTML file with embedded CSS and JavaScript. No external dependencies beyond Google Fonts.

- **Cost formula**: `tokens × model_distribution × token_split × price_per_1M_tokens / 1,000,000`
- **Currency conversion**: USD base prices × exchange rate
- **Tier fallback**: If a model isn't available in the selected tier, it falls back to Global pricing (with a ⚠ indicator)

## 📝 License

MIT

## 🙏 Inspired By

This project was inspired by [**Spending Tokens**](https://github.com/shane-theinfo/token-costs) by Shane Burke at *The Information*, which provides a similar interactive token cost calculator for AI model providers (Anthropic, OpenAI, Google, Meta, etc.). This Azure-focused version adapts the concept for Microsoft Azure's model ecosystem with deployment tier, region, and currency support.
