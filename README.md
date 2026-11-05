# cramer-check

An unofficial Claude skill that scores a stock against the rules in Jim Cramer's book *How to Make Money in Any Market* (Simon & Schuster, 2025).

> **Independent student project.** Not affiliated with, endorsed by, or reviewed by Jim Cramer, CNBC, or the book's publisher. Not investment advice. The book's rules are paraphrased in my own words, with chapter references so every claim can be checked against the book. Buy the book.

## What it does

Ask Claude to "run cramer-check on <stock>". The skill makes Claude:

1. **Fetch fresh data first** (latest-quarter growth, margins, P/E vs peers, PEG, debt vs cash flow, 3-year profit/loss history, guidance, management or legal red flags). It never scores from memory.
2. **Gate 1: Eliminate.** Deep cyclicals, credit-risk financials, concept companies without earnings, low-growth "safe" stocks, high fixed-cost businesses, suffocating debt, and non-investments. One fail means no slot in the portfolio. The stock can still go on a watchlist.
3. **Gate 2: Hero test.** Secular growth, best of breed, the troika (growth, management, gross margins), recession test, scale, beat-and-raise record, earnings quality, and catalysts.
4. **Gate 3: Valuation.** P/E against the index and peers, PEG, and the Rule of 40 for loss-makers.
5. **Output a scorecard.** Pass, borderline or fail for each rule, with the number behind it and a confidence tag. It ends with the "three reasons to own it" street test and the sell triggers to watch next quarter.

It also encodes the book's portfolio structure (50% index, five stocks, one hedge), buying and holding discipline, and sell rules.

## India adaptation (my addition, not from the book)

The sections marked **India adaptation** in `SKILL.md` map the framework to Indian markets: Nifty 50 as the index, a gold ETF as the hedge, and checks for India-specific risks the book doesn't cover (promoter pledging, related-party transactions, PSU ownership risk, SEBI and USFDA actions). These mappings are my own judgment, not Cramer's.

## Status and limits

- The skill's output is only as good as the data Claude retrieves. Always check figures against the exchange filings.
- Verdicts are a rules-based screen, not a prediction.
- I'm still testing whether the rules hold up on Indian stocks over 2015 to 2025. **No backtest results are published yet**, and nothing here claims the rules work in India.

## Install

Add `SKILL.md` as a custom skill in Claude, then ask: *"run cramer-check on <company>"*.

## Files

- `SKILL.md`: the skill itself.
- `sample-scorecard.pdf`: an example output (illustration only).

## Author

Swayam Kondapalli, final-year B.Tech CS, Mahindra University, Hyderabad.
GitHub: [@googly0](https://github.com/googly0)
