# Topic

Portfolio-Management-Using-RL

# Abstract

Portfolio Management

> To make the most of one's investment portfolio investors must participate actively in portfolio
management.

> By doing so, they will not only be able to cushion their resources against market risks will 
but will also be able to maximise their returns successfully.

What is Portfolio Management?

Portfolio management's meaning can be explained as the process of managing individuals'
investments so that they maximise their earnings within a given time horizon. 

Furthermore, such practices ensure that the capital invested by individuals is not exposed to too much market risk.
The entire process is based on the ability to make sound decisions. 
Typically, such a decision relates to-achieving a profitable investment mix, allocating assets as per risk and financial goals and
diversifying resources to combat capital erosion.


Why is Portfolio Management is important?

Portfolio management is important because it covers a certain amount of risk through diversification and shuffling of funds among different assets according to the returns they are generating. 
It also helps in planning regarding tax obligations. Moreover, it helps in arranging funds in times of emergencies.

Reinforcement learning (RL) trains an agent to solve tasks by trial and error, while DRL uses deep neural networks as function approximators. DRL balances exploration (of uncharted territory) and exploitation (of current knowledge), and has been recognized as a competitive edge for automated trading. DRL framework is powerful in solving dynamic decision making problems by learning through interactions with an unknown environment, thus provides two major advantages: portfolio scalability and market model independence. In quantitative finance, automated trading is essentially making dynamic decisions, namely to decide where to trade, at what price, and what quantity, over a highly stochastic and complex stock market. Taking many complex financial factors into account, DRL trading agents build a multi-factor model and provide algorithmic trading strategies, which are difficult for human traders.

# Working

# Designing DRL i.e Deep Reinforcement Learning trading strategy includes:
 • Pre-processing market data 
 
 Data preprocessing is a crucial step for training a high quality machine learning model. We need to check for missing data and do feature engineering in order to convert the data into a model-ready state.

Add technical indicators. In practical trading, various information needs to be taken into account, for example the historical stock prices, current holding shares, technical indicators, etc. In this article, we demonstrate two trend-following technical indicators: MACD and RSI.
Add turbulence index. Risk-aversion reflects whether an investor will choose to preserve the capital. It also influences one's trading strategy when facing different market volatility level. To control the risk in a worst-case scenario, such as financial crisis of 2007–2008, FinRL employs the financial turbulence index that measures extreme asset price fluctuation.
 
 • Building a training. environment 
 Considering the stochastic and interactive nature of the automated stock trading tasks, a financial task is modeled as a Markov Decision Process (MDP) problem. The training process involves observing stock price change, taking an action and reward's calculation to have the agent adjusting its strategy accordingly. By interacting with the environment, the trading agent will derive a trading strategy with the maximized rewards as time proceeds.

Our trading environments, based on OpenAI Gym framework, simulate live stock markets with real market data according to the principle of time-driven simulation.

The action space describes the allowed actions that the agent interacts with the environment. Normally, action a includes three actions: {-1, 0, 1}, where -1, 0, 1 represent selling, holding, and buying one share. Also, an action can be carried upon multiple shares. We use an action space {-k,…,-1, 0, 1, …, k}, where k denotes the number of shares to buy and -k denotes the number of shares to sell. For example, "Buy 10 shares of AAPL" or "Sell 10 shares of AAPL" are 10 or -10, respectively. The continuous action space needs to be normalized to [-1, 1], since the policy is defined on a Gaussian distribution, which needs to be normalized and symmetric.


 
 • Managing trading state 
 
 Assume that we have $1,000,000 initial capital at 2020-07-01. We use the DDPG model to trade NIFTY 50 stocks.
 
 Set turbulence threshold
 
Set the turbulence threshold to be greater than the maximum of insample turbulence data, if current turbulence index is greater than the threshold, then we assume that the current market is volatile
 
Trade
DRL model needs to update periodically in order to take full advantage of the data, ideally we need to retrain our model yearly, quarterly, or monthly. We also need to tune the parameters along the way, in this notebook I only use the in-sample data from 2009-01 to 2020-07 to tune the parameters once, so there is some alpha decay here as the length of trade date extends.

Numerous hyperparameters – e.g. the learning rate, the total number of samples to train on – influence the learning process and are usually determined by testing some variations. 
 

 
 • backtesting trading performance
 
 Backtesting plays a key role in evaluating the performance of a trading strategy. Automated backtesting tool is preferred because it reduces the human error. We usually use the Quantopian pyfolio package to backtest our trading strategies. It is easy to use and consists of various individual plots that provide a comprehensive image of the performance of a trading strategy.
 
 
 # Learning Algorithms :
   1] DDQN 
   
   2] PPO 
   
   3] DDPG 
   
   4] A2C 
   


# Installation setting

 > FinRL Library

• Open-source 
• Provides development Pipe-line for trading strategy.

# Documentation of FinRL library.
below is the link:

https://finrl.readthedocs.io/en/latest/

>Installation of FinRL Library

Since AI4finance community is  
still actively updating the FinRL repository, please install the unstable development version of FinRL using pip:


pip install git+https://github.com/AI4Finance-Foundation/FinRL.git





