# Elite Confluence Engine Pro V2 - Indicator & Strategy

This repository contains a professional-grade trading toolkit for TradingView, featuring both a sophisticated signal indicator and a fully backtestable strategy version. This allows for both real-time signal analysis and rigorous historical performance testing.

## New in V4: Performance & Usability Overhaul

Based on expert feedback regarding complexity and performance, this version introduces major new features to make the script more robust, practical, and user-friendly.

*   **Tuning Presets:** Located in the new "🚀 Performance & Presets" section of the settings, you can now choose between several tuning presets:
    *   `Custom`: Uses your manual settings below.
    *   `Balanced`: A good starting point for all-around performance.
    *   `High Frequency`: Adjusts weights and thresholds to generate more signals, potentially capturing smaller moves.
    *   `High Confluence`: Uses stricter settings, waiting for only the highest probability setups.
*   **Performance Mode:** You can now choose between `Full` and `Fast` mode. `Fast` mode disables the most computationally heavy features (like Supply/Demand analysis and the data table) to ensure the script runs smoothly on any device or chart.

## Project Overview

The core of this project is the "Elite Confluence Engine," a powerful Pine Script that uses a multi-faceted scoring system to identify high-probability trading setups. It analyzes Trend, Momentum, Market Structure, Order Flow, and Smart Money Concepts to generate a confluence score for both bullish and bearish scenarios.

To provide maximum flexibility, the project is split into two files:

*   **`ECE_Pro_V2_Indicator.pine`**: An advanced indicator for generating real-time buy and sell signals directly on your chart. It is rich in visual aids like heatmaps, S/R levels, and a data table. Use this for discretionary trading.
*   **`ECE_Pro_V2_Strategy.pine`**: A full-fledged backtesting strategy based on the indicator's logic. Use this to test the system's historical performance, optimize its parameters, and understand its statistical behavior (e.g., win rate, profit factor, drawdown).

## Key Features of the Strategy Script

The `ECE_Pro_V2_Strategy.pine` script is more than just an indicator. It has been enhanced with features essential for a "best-in-class" trading tool:

*   **Backtesting Engine:** Simulates trades based on the script's signals, allowing you to see how it would have performed historically.
*   **Realistic Costs:** Configured with default commission and slippage to provide more realistic backtesting results.
*   **Dynamic Take-Profit:** In addition to a fixed Risk-to-Reward ratio, the strategy includes a **Dynamic RSI Exit** mode. This mode attempts to maximize profit by holding a trade until momentum shows signs of reversal, rather than exiting at a fixed target.
*   **Trend Reversal Exit:** The strategy includes logic to automatically exit a trade if the underlying trend conditions significantly reverse, helping to protect profits.

### New in V3: Beginner Mode

To make the script more accessible for all users, a **"Beginner Mode"** has been added to the visual settings.

*   **What it does:** When enabled, it hides all advanced on-chart visuals (the data table, heatmap, MA ribbons, S/R lines, etc.), leaving a clean chart that only shows the essential BUY and SELL arrows and the suggested Stop Loss/Take Profit levels for each trade, labeled with their exact prices.
*   **How to use it:** Go into the script's "Settings" on your TradingView chart, find the "Visual & Alert Settings" section, and check the "Enable Beginner Mode" box.

## How to Use the **Indicator**

1.  Open a chart on [TradingView](https://www.tradingview.com/).
2.  Open the **Pine Editor** from the bottom panel.
3.  Copy the entire code from the `ECE_Pro_V2_Indicator.pine` file.
4.  Paste the code into the Pine Editor, replacing any existing text.
5.  Click **"Add to Chart"**. The signals and visuals will appear on your chart.

## How to Use the **Strategy** and Backtester

1.  Open a chart on [TradingView](https://www.tradingview.com/).
2.  Open the **Pine Editor**.
3.  Copy the entire code from the `ECE_Pro_V2_Strategy.pine` file.
4.  Paste the code into the Pine Editor.
5.  Click **"Add to Chart"**.
6.  At the bottom of the chart, open the **"Strategy Tester"** panel.
7.  In the Strategy Tester panel, you can view the backtesting results:
    *   **Overview:** Shows the equity curve, drawdown, net profit, and a list of trades.
    *   **Performance Summary:** Provides detailed statistics like Profit Factor, Win Rate, Average Trade, etc.
    *   **Properties:** Allows you to configure the strategy's input parameters (e.g., MA lengths, signal strength, take-profit mode) and see how they affect performance.

## Configuration Highlights

Both scripts are highly configurable via the "Settings" menu. In the strategy script, a key new setting is:

*   **Take Profit Mode**:
    *   `Fixed R:R`: Exits a trade when the price hits a take-profit level calculated from a fixed risk-to-reward ratio (e.g., 2.5R).
    *   `Dynamic RSI Exit`: Ignores the fixed take-profit level and instead closes the trade only when the RSI indicates that momentum is fading (e.g., crossing back from overbought/oversold). This can lead to larger wins but may also result in giving back some profit from the peak.