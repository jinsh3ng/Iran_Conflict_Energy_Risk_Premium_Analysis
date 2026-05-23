# 📈 Israel-Iran Conflict — Energy Risk Premium Analysis

## 1. Overview

Risk premiums typically increase during crises, especially wartime, as uncertainty drives investors to demand higher returns. This project analyzes how risk premiums evolve **before**, **during**, and **after** key conflict-related events involving Iran in June 2025:

- **Israel attacks Iran** — *2025-06-13*
- **USA attacks Iran** — *2025-06-22*
- **Ceasefire announced** — *2025-06-24*

To conduct this analysis, we focus on **natural gas** and **crude oil** futures, as they are highly sensitive to geopolitical developments, particularly in the Middle East — a region critical to global energy supply. For natural gas, we selected **TTF=F**, and for crude oil, **BZ=F**. Price data was extracted using the `yfinance` library.

> [!NOTE]
> I conducted this analysis because I was curious — nothing groundbreaking, just myself coding and combining my finance knowledge into analytics.

## 2. 📁 Project Structure

```
Israel-Iran-Risk-Premium-Analysis/
├── src/
│   └── analyze_conflict.py    # Core analysis and plotting logic
├── main.ipynb                 # Run the analysis here
├── requirements.txt           # Python dependencies
└── README.md
```

## 3. ⚙️ Setup Instructions

1. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the analysis in `main.ipynb`

---

## 4. 🔍 Key Findings

> [!IMPORTANT]
> This analysis uses **daily closing prices** from `yfinance`. Intraday price reactions are not captured, and timezone differences between event announcements and market closing times may introduce a one-day lag — meaning the immediate shock on the day of each event may be understated.

### ⚔️ Israel Attack (June 13)

Both TTF and BZ=F showed positive risk premiums that increased, peaking after four trading days before declining ahead of the US attack. This drop likely reflects how, after the initial fear spike, traders realized the conflict was not escalating further and was unlikely to severely disrupt global energy markets.

| Ticker | Avg Premium | Peak |
|--------|-------------|------|
| **TTF=F** | +1.61 USD | +5.57 USD on day 4 |
| **BZ=F** | +0.92 USD | +6.97 USD on day 3 |

---

### ⚔️ US Attack (June 22)

Both TTF and BZ=F turned negative — an unexpected outcome. This significant underpricing suggests traders believed Iran would not retaliate and would likely agree to a ceasefire, especially given the destruction of its nuclear plants. The market appears to have acted **efficiently**, in line with market hypothesis theory, as investors correctly anticipated a quick resolution.

| Ticker | Avg Premium |
|--------|-------------|
| **TTF=F** | -3.75 USD |
| **BZ=F** | -9.69 USD |

---

### 🕊️ Ceasefire (June 24)

Both TTF and BZ=F exhibited steadily decreasing risk premiums following the ceasefire announcement, as investor sentiment improved and geopolitical uncertainty **receded**.

| Ticker | Avg Premium | Change |
|--------|-------------|--------|
| **TTF=F** | -5.35 USD | Further 43% decline |
| **BZ=F** | -9.69 USD | Sustained negative premium |

---

## 5. 📌 Conclusions

The **type and perceived escalation** of conflict significantly influences risk premiums. Initial attacks tend to increase premiums as uncertainty spikes, but escalations can lead to declines when markets efficiently anticipate a resolution and price in the expected outcome early. This highlights the role of market efficiency in rapidly incorporating new information during geopolitical events.

That said, a few limitations should be kept in mind. Since this analysis relies on **daily closing prices**, any intraday reactions to news announcements are not captured, and timezone differences may shift the observed impact by a day. The linear regression baseline also carries a low R² by design — energy prices are inherently noisy and non-linear, so the regression is not intended as a predictive model but simply as a neutral pre-event trend to measure deviations against. Additionally, the post-ceasefire window only covers **4 trading days**, so those findings should be interpreted cautiously.

---

Developed by **jinsh3ng**
