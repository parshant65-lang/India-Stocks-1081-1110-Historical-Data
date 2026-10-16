# India-Stocks-1081-1110-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1081 to 1110)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1081-1110-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1081 to 1110)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1081 | `FEDDERSHOL` | Fedders Holding Limited | `FEDDERSHOL.NS` |
| 1082 | `FEDFINA` | Fedbank Financial Services Limited | `FEDFINA.NS` |
| 1083 | `FEL` | Future Enterprises Limited | `FEL.NS` |
| 1084 | `FELDVR` | Future Enterprises Limited | `FELDVR.NS` |
| 1085 | `FERMENTA` | Fermenta Biotech Limited | `FERMENTA.NS` |
| 1086 | `FIBERWEB` | Fiberweb (India) Limited | `FIBERWEB.NS` |
| 1087 | `FIEMIND` | Fiem Industries Limited | `FIEMIND.NS` |
| 1088 | `FILATEX` | Filatex India Limited | `FILATEX.NS` |
| 1089 | `FILATFASH` | Filatex Fashions Limited | `FILATFASH.NS` |
| 1090 | `FINEORG` | Fine Organic Industries Limited | `FINEORG.NS` |
| 1091 | `FINKURVE` | Finkurve Financial Services Limited | `FINKURVE.NS` |
| 1092 | `FINOPB` | Fino Payments Bank Limited | `FINOPB.NS` |
| 1093 | `FINPIPE` | Finolex Industries Limited | `FINPIPE.NS` |
| 1094 | `FISCHER` | Fischer Medical Ventures Limited | `FISCHER.NS` |
| 1095 | `FLAIR` | Flair Writing Industries Limited | `FLAIR.NS` |
| 1096 | `FLEXITUFF` | Flexituff Ventures International Limited | `FLEXITUFF.NS` |
| 1097 | `FLFL` | Future Lifestyle Fashions Limited | `FLFL.NS` |
| 1098 | `FMGOETZE` | Federal-Mogul Goetze (India) Limited. | `FMGOETZE.NS` |
| 1099 | `FMNL` | Future Market Networks Limited | `FMNL.NS` |
| 1100 | `FOCUS` | Focus Lighting and Fixtures Limited | `FOCUS.NS` |
| 1101 | `FOODSIN` | Foods & Inns Limited | `FOODSIN.NS` |
| 1102 | `FOSECOIND` | Foseco India Limited | `FOSECOIND.NS` |
| 1103 | `FREDUN` | Fredun Pharmaceuticals Limited | `FREDUN.NS` |
| 1104 | `FRONTSP` | Frontier Springs Limited | `FRONTSP.NS` |
| 1105 | `FUSION` | Fusion Finance Limited | `FUSION.NS` |
| 1106 | `GAEL` | Gujarat Ambuja Exports Limited | `GAEL.NS` |
| 1107 | `GAJA` | Gaja Alternative Asset Management Limited | `GAJA.NS` |
| 1108 | `GALAPREC` | Gala Precision Engineering Limited | `GALAPREC.NS` |
| 1109 | `GALAXYSURF` | Galaxy Surfactants Limited | `GALAXYSURF.NS` |
| 1110 | `GANDHAR` | Gandhar Oil Refinery (India) Limited | `GANDHAR.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream FEDDERSHOL 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1081-1110-Historical-Data/main/FEDDERSHOL/1m/2026/10/FEDDERSHOL_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
