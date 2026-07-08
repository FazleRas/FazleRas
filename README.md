# Fazle Rasool

Computer Science student at Oakton College (Chicago, IL). I build full-stack applications and developer tooling, mostly around quantitative and data-heavy problems - taking market data, code diffs, and messy inputs and turning them into systems that measure their own behavior.

My recent work sits where data analysis meets practical engineering: financial backtesting, LLM tooling, and clean APIs I can actually deploy and use.

Outside of code I'm into cars and building things with my hands, as well as travelling!

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

## Featured Projects

### [AlphaLab](https://github.com/FazleRas/AlphaLab): full-stack trading analytics platform

A React + FastAPI platform for equity research and strategy backtesting. It computes technical indicators (SMA20/50, RSI, MACD) from raw OHLCV data using pandas, runs multi-strategy backtests (RSI, MACD, combined, golden cross), and reports real risk metrics — compounded return, annualized CAGR, annualized Sharpe ratio, max drawdown, and win rate — benchmarked against both buy-and-hold and SPY.

The part I'm most proud of is the overfitting story: a parameter-sweep heatmap surfaces whether an edge is a robust *region* of good parameters or a single lucky cell, and out-of-sample validation splits history ~70/30, re-optimizes on the training window only, then re-tests the winners blind on the held-out window with an honest held-up / lagged / degraded verdict. Indicators are computed over the full series before slicing, so there's no lookahead leak.

**Stack:** Python, FastAPI, pandas, yfinance, Docker · React, Tailwind, Recharts · deployed on Render + Vercel
**Live demo:** https://alphalab-lime.vercel.app

### [acrobot](https://github.com/FazleRas/acrobot): AI code-review GitHub Action

A GitHub Action that reviews pull-request diffs with an LLM and posts inline comments, engineered so that being wrong is cheap and being spammy is impossible. It fetches changed hunks through the GitHub API (it never checks out or executes the code it reviews), validates every finding's line anchor against the parsed diff before posting, and batches everything into a single review.

I built it around the Gemini free tier as a hard constraint, which forced the parts that actually matter: a two-clock rate limiter (per-minute window + daily budget) with graceful partial-review degradation instead of a red CI failure, schema-validated LLM outputs treated as untrusted input, and content-based fingerprints that keep re-runs idempotent across force-pushes. It ships with a 24-test suite and reviews its own pull requests.

**Stack:** Python, GitHub Actions, Gemini, httpx, uv, pytest

## Also here

[TextDNA](https://github.com/FazleRas/TextDNA) is a small web app that analyzes your typing style. There are also a couple of early front-end builds — a physics equation calculator and a basic calculator app — from when I was first getting comfortable with JavaScript.

## Currently

Extending AlphaLab with per-user watchlists and auth (Supabase), and building out acrobot's eval harness with labeled diff cases and precision/recall reporting. I'm interested in backend, data engineering, and quantitative tooling roles.

- Chicago, IL
- LinkedIn: [in/fazle-rasool-m](https://www.linkedin.com/in/fazle-rasool-m)

![Fazle's GitHub stats](https://github-readme-stats.vercel.app/api?username=FazleRas&show_icons=true&theme=tokyonight)

---

<sub>Built with too much coffee and a soft spot for clean APIs.</sub>

![Made with love](https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=flat-square)
![Profile views](https://komarev.com/ghpvc/?username=FazleRas&label=Profile%20views&color=blueviolet&style=flat-square)
