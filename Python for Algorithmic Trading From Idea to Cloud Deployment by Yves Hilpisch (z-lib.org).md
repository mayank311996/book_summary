# Python for Algorithmic Trading From Idea to Cloud Deployment by Yves Hilpisch 

## Preface 

- This is a book about Python for algorithmic trading, primarily in the context
of alpha generating strategies. (p5)
- http://py4at.pqp.io/ (p7)
- This book covers: 
    1. Chapter 1, Python and Algorithmic Trading
The first chapter is an introduction to the topic of algorithmic trading—
that is, the automated trading of financial instruments based on computer
algorithms. It discusses fundamental notions in this context and also
addresses, among other things, what the expected prerequisites for
reading the book are.
    2. Chapter 2, Python Infrastructure
This chapter lays the technical foundations for all subsequent chapters in
that it shows how to set up a proper Python environment. This chapter
mainly uses conda as a package and environment manager. It illustrates
Python deployment via Docker containers and in the cloud.
    3. Chapter 3, Working with Financial Data
Financial time series data is central to every algorithmic trading project.
This chapter shows you how to retrieve financial data from different
public data and proprietary data sources. It also demonstrates how to
store financial time series data efficiently with Python.
    4. Chapter 4, Mastering Vectorized Backtesting
Vectorization is a powerful approach in numerical computation in general
and for financial analytics in particular. This chapter introduces
vectorization with NumPy and pandas and applies that approach to the
backtesting of SMA-based, momentum, and mean-reversion strategies.
    5. Chapter 5, Predicting Market Movements with Machine LearningThis chapter is dedicated to generating market predictions by the use of
machine learning and deep learning approaches. By mainly relying on
past return observations as features, approaches are presented for
predicting tomorrow’s market direction by using such Python packages as
Keras in combination with TensorFlow and scikit-learn .
    6. Chapter 6, Building Classes for Event-Based Backtesting
While vectorized backtesting has advantages when it comes to
conciseness of code and performance, it’s limited with regard to the
representation of certain market features of trading strategies. On the
other hand, event-based backtesting, technically implemented by the use
of object oriented programming, allows for a rather granular and more
realistic modeling of such features. This chapter presents and explains in
detail a base class as well as two classes for the backtesting of long-only
and long-short trading strategies.
    7. Chapter 7, Working with Real-Time Data and Sockets
Needing to cope with real-time or streaming data is a reality even for the
ambitious individual algorithmic trader. The tool of choice is socket
programming, for which this chapter introduces ZeroMQ as a lightweight
and scalable technology. The chapter also illustrates how to make use of
Plotly to create nice looking, interactive streaming plots.
    8. Chapter 8, CFD Trading with Oanda
Oanda is a foreign exchange (forex, FX) and Contracts for Difference
(CFD) trading platform offering a broad set of tradable instruments, such
as those based on foreign exchange pairs, stock indices, commodities, or
rates instruments (benchmark bonds). This chapter provides guidance on
how to implement automated algorithmic trading strategies with Oanda,
making use of the Python wrapper package tpqoa .
    9. Chapter 9, FX Trading with FXCMFXCM is another forex and CFD trading platform that has recently
released a modern RESTful API for algorithmic trading. Available
instruments span multiple asset classes, such as forex, stock indices, or
commodities. A Python wrapper package that makes algorithmic trading
based on Python code rather convenient and efficient is available
(http://fxcmpy.tpq.io).
    10. Chapter 10, Automating Trading Operations
This chapter deals with capital management, risk analysis and
management, as well as with typical tasks in the technical automation of
algorithmic trading operations. It covers, for instance, the Kelly criterion
for capital allocation and leverage in detail.

## Chapter 1: Python and Algorithmic Trading 

- One major obstacle to the adoption of Python in the financial industry has
been the fact that the default Python version, called CPython, is an
interpreted, high-level language. Numerical algorithms in general and
financial algorithms in particular are quite often implemented based on
(nested) loop structures. While compiled, low-level languages like C or C++
are really fast at executing such loops, Python, which relies on interpretationinstead of compilation, is generally quite slow at doing so. As a
consequence, pure Python proved too slow for many real-world financial
applications, such as option pricing or risk management. (p18-19)
- Performance comparison code (p20-22)
- Vectorization is a powerful concept for writing concise, easy-to-read, and easy-to-maintain
code in finance and algorithmic trading. With NumPy , vectorized code does not only make
code more concise, but it also can speed up code execution considerably (by a factor of
about eight in the Monte Carlo simulation, for example). (p22)
- Open data source - http://quandl.com/
- Read Code about using Quandl to get data (p23-25)
- Like NumPy , pandas
allows for rather concise, vectorized code that is also generally executed quite fast due to
heavy use of compiled code under the hood. (p25)
- "Trading in financial markets is an important economic activity. Trades
are necessary to get into and out of the market, to put unneeded cash
into the market, and to convert back into cash when the money is
wanted. They are also needed to move money around within the market,
to exchange one asset for another, to manage risk, and to exploit
information about future price movements." (p26)
- Some trading motives of people and financial institution managing money: Beta trading, 
Alpha generation, Static hedging, Dynamic hedging, Asset-liability management, Market making (p26-27)
- This book focuses on algorithmic trading in the context of alpha generating
strategies. Although there are more sophisticated definitions for alpha, for
the purposes of this book, alpha is seen as the difference between a trading
strategy’s return over some period of time and the return of the benchmark
(single stock, index, cryptocurrency, etc.). For example, if the S&P 500
returns 10% in 2018 and an algorithmic strategy returns 12%, then alpha is
+2% points. If the strategy returns 7%, then alpha is -3% points. In general,
such numbers are not adjusted for risk, and other risk characteristics, such as
maximal drawdown (period), are usually considered to be of second order
importance, if at all. (p28)
- This book focuses on alpha-generating strategies, or strategies that try to generate positive
returns (above a benchmark) independent of the market’s performance. Alpha is defined
in this book (in the simplest way) as the excess return of a strategy over the benchmark
financial instrument’s performance. (p28)
- There are other areas where trading-related algorithms play an important
role. One is the high frequency trading (HFT) space, where speed is
typically the discipline in which players compete. 6 The motives for HFT are
diverse, but market making and alpha generation probably play a prominentrole. Another one is trade execution, where algorithms are deployed to
optimally execute certain nonstandard trades. Motives in this area might
include the execution (at best possible prices) of large orders or the
execution of an order with as little market and price impact as possible. A
more subtle motive might be to disguise an order by executing it on a number
of different exchanges. (p28-29)
- Read table 1-0 (p30)
- Compared to the S&P 500, hedge fund performance overall was quite
meager for the year 2017. While the S&P 500 index returned 21.8%, hedge
funds only returned 8.5% to investors (see this article in Investopedia). This
illustrates how hard it is, even with multimillion dollar budgets for research
and technology, to generate alpha. (p30)
- Some reasons behind Python for algotrading (p31-32)
    1. Data analytics capabilities 
    2. Handling of modern APIs: FXCM and Oanda offer RESTful application programming interfaces (APIs) and socket
(streaming) APIs to access historical and live data. Python is in general
well suited to efficiently interact with such APIs.
    3. Dedicated packages: PyAlgoTrade and Zipline for the backtesting of trading
strategies and Pyfolio for performing portfolio and risk analysis.
    4. Vendor sponsored packages: Bloomberg and Refinitiv
    5. Dedicated platforms: Quantopian, for example, offers a standardized backtesting environment
as a Web-based platform where the language of choice is Python andwhere people can exchange ideas with like-minded others via different
social network features. 
    6. Buy- and sell-side adoption 
    7. Education, training, and books 
- Throughout this book, four different algorithmic trading strategies are used as
examples. They are introduced briefly in the following sections and in some
more detail in Chapter 4. All these trading strategies can be classified as
mainly alpha seeking strategies, since their main objective is to generate
positive, above-market returns independent of the market direction. (p34)
    1. Simple Moving Averages 
    2. Momentum
    3. Mean Reversion 
    4. Machine and Deep Learning 
- Be aware of the fact that the algorithmic trading world in
general is secretive and that almost everyone who is successful is naturally reluctant to
share their secrets in order to protect their sources of success (that is, their alpha). (p35)
- Python is already a force in finance in general and is on its way to becoming
a major force in algorithmic trading. (p35)

## Chapter 2: Python Infrastructure (p39)

- Virtual environment manager: conda or virtualenv (p40)
- Explore this chapter if needed. Not necessary. 

## Chapter 3: Working with Financial Data (p75)

```
Clearly, data beats algorithms. Without comprehensive data, you tend to
get non-comprehensive predictions.
—Rob Thomas (2016)
```

- Read table3-1 (p75)
- This book is mainly concerned with structured data (numerical, tabular
data) of both historical and real-time types. (p75)
- “Working with Open Data Sources”
introduces Quandl as a popular open data source platform. “Eikon Data API”introduces the Python wrapper for the Refinitiv Eikon Data API. Finally,
“Storing Financial Data Efficiently” briefly shows how to store historical,
structured data efficiently with pandas based on the HDF5 binary storage
format. (p75-76)
- Read code - Reading financial data from different sources (p76-83)
- Read code - Working with open data sources (p83-88)
    - https://www.quandl.com/tools/python (p84)
    - https://www.quandl.com/data/BCHAIN/MKPRU-Bitcoin-Market-Price-USD (p84)
    - Open source software is a trend that started many years ago. It has lowered the barriers
to entry in many areas and also in algorithmic trading. A new, reinforcing trend in this
regard is open data sources. In some cases, such as with Quandl, they even provide high
quality data sets. It cannot be expected that open data will completely replace professional
data subscriptions any time soon, but they represent a valuable means to get started with
algorithmic trading in a cost efficient manner. (p88)
- Read code - Eikon data API (p88-99)
    - http://refinitiv.com/ (p88)
    - https://www.refinitiv.com/en/products/eikon-trading-software (p88)
    - https://www.bloomberg.com/professional/ (p88)
    - https://developers.refinitiv.com/en (p89)
    - https://developers.refinitiv.com/en/api-catalog/eikon/eikon-data-api/quick-start (p89)
- Read code - Storing financial data efficiently (p100-114)
    - Using the HDFStore wrapper for the HDF5 binary storage standard, pandas is able to
write and read financial data almost at the maximum speed the available hardware allows.
Exports to other file-based formats, like CSV, are generally much slower alternatives. (p106)
    - The two
approaches introduced in this sub-section are convenient and efficient when
you are working with more or less immutable data sets that fit into memory.
Nowadays, algorithmic trading, however, has to deal in general with
continuously and rapidly growing data sets like, for example, tick data with
regard to stock prices or foreign exchange rates. To cope with the
requirements of such a scenario, alternative approaches might prove useful. (p106)
    - Admittedly, such simple queries are also possible with pandas if the data set
fits into memory. However, the SQL query language has proven useful and
powerful for decades now and should be in the algorithmic trader’s arsenal
of data weapons. (p114)
    - pandas also supports database connections via SQLAlchemy , a Python abstraction layer
package for diverse relational databases (refer to the SQLAlchemy home page). This in
turn allows for the use of, for example, MySQL as the relational database backend. (p114)
- Read code - Python Scripts (p115-117)
    - Of course, multiple DataFrame objects could also be stored in a single HDFStore object. (117)
    
## Chapter 4: Mastering Vectorized Backtesting (p118)

```
[T]hey were silly enough to think you can look at the past to predict the
future. 1
—The Economist
```

- Strategies covered in this chapter: (p118)
    1. Simple moving averages (SMA) based strategies 
    2. Momentum strategies 
    3. Mean-reversion strategies 
- Vectorized backtesting should be considered in the following cases: (p119-120)
    1. Simple trading strategies 
    2. Interactive strategy exploration 
    3. Visualization as major goal 
    4. Comprehensive backtesting programs 
- Read code - Making use of vectorization (p120-127)
    - The standard instruction set and data model of Python does not generally allow for
vectorized numerical operations. NumPy introduces powerful vectorization techniques
based on the regular array class ndarray that lead to concise code that is close to
mathematical notation in, for example, linear algebra regarding vectors and matrices. (p123)
    - While NumPy brings general vectorization approaches to the numerical computing world of
Python, pandas allows vectorization over time series data. This is really helpful for the
implementation of financial algorithms and the backtesting of algorithmic trading strategies.
By using this approach, you can expect concise code, as well as a faster code execution, in
comparison to standard Python code, making use of for loops and similar idioms to
accomplish the same goal. (p127)
- Read code - Strategies based on simple moving averages (p127-138)
    - pandas proves to be a powerful tool for the vectorized analysis of trading strategies.
Many statistics of interest, such as log returns, cumulative returns, annualized returns and
volatility, maximum drawdown, and maximum drawdown period, can in general be
calculated by a single line or just a few lines of code. Being able to visualize results by a
simple method call is an additional benefit. (p136)
- Read code - Strategies based on momentum (p139-147)
    - Two types: cross sectional momentum strategies and time series momentum strategies (p139)
- Read code - Strategies based on Mean Reversion (p148-153)
- The ability to show examples with good results often comes at the cost of
data snooping. According to White (2000), data snooping can be defined as
follows:
Data snooping occurs when a given set of data is used more than once
for purposes of inference or model selection. (p154)
- Another problem that arises in this context is overfitting. Overfitting in a
trading context can be described as follows (see the Man Institute on
Overfitting):
Overfitting is when a model describes noise rather than signal. The
model may have good performance on the data on which it was tested,
but little or no predictive power on new data in the future. Overfitting
can be described as finding patterns that aren’t actually there. There is
a cost associated with overfitting—an overfitted strategy will
underperform in the future. (p154)
- Recent advances in algorithmic research and high-performance
computing have made it nearly trivial to test millions and billions of
alternative investment strategies on a finite dataset of financial time
series....[I]t is common practice to use this computational power to
calibrate the parameters of an investment strategy in order to maximize
its performance. But because the signal-to-noise ratio is so weak, often
the result of such calibration is that parameters are chosen to profit
from past noise rather than future signal. The outcome is an overfit
backtest. (p155)
- The chapter
admittedly makes a number of simplifying assumptions, and a rigorous
backtesting of trading strategies needs to take into account more factors that
determine trading success in practice, such as data issues, selection issues,
avoidance of overfitting, or market microstructure elements. However, the
major goal of the chapter is to focus on the concept of vectorization and what
it can do in algorithmic trading from a technological and implementation
point of view. With regard to all concrete examples and results presented, the
problems of data snooping, overfitting, and statistical significance need to be
considered. (p156)
- Read Python scripts (p159-166)

## Chapter 5: Predicting Market Movements with Machine Learning (p167)

- This chapter includes the following strategies: (p167)
    - Linear regression-based strategies 
    - Machine learning-based strategies 
    - Deep learning-based strategies 
- The major goal of this chapter is to provide practical approaches to predict
future price movements in financial markets based on past returns. The basic
assumption is that the efficient market hypothesis does not hold universally
and that, similar to the reasoning behind the technical analysis of stock price
charts, the history might provide some insights about the future that can be
mined with statistical techniques. In other words, it is assumed that certain
patterns in financial markets repeat themselves such that past observations
can be leveraged to predict future price movements. More details are
covered in Hilpisch (2020). (p168)
- Read code - Using linear regression for market movement prediction (p168-186)
    - The optimal regression parameters illustrate what is typically called the
random walk hypothesis. This hypothesis states that stock prices or exchange
rates, for example, follow a random walk with the consequence that the best
predictor for tomorrow’s price is today’s price. The optimal parameters
seem to support such a hypothesis since today’s price almost completely
explains the predicted price level for tomorrow. The four other values hardly
have any weight assigned. (p176)
    - Applying linear OLS regression to predict rates for EUR/USD based on historical rates
provides support for the random walk hypothesis. The results of the numerical example
show that today’s rate is the best predictor for tomorrow’s rate in a least-squares sense. (p177)
    - So far, the analysis is based on absolute rate levels. However, (log) returns
might be a better choice for such statistical applications due to, for example,
their characteristic of making the time series data stationary. The code to
apply linear regression to the returns data is almost the same as before. This
time it is not only today’s return that is relevant to predict tomorrow’s return,
but the regression results are also completely different in nature. (p178)
    - From a trading point of view, one might argue that it is not the magnitude of
the forecasted return that is relevant, but rather whether the direction isforecasted correctly or not. (p179-180)
    - It is well
known that the ten best and worst days in the markets for a given period of
time considerably influence the overall performance of investments. 2 In an
ideal world, a long-short trader would try, of course, to benefit from both
best and worst days by going long and short, respectively, on the basis of
appropriate market timing indicators. Translated to the current context, this
implies that, in addition to the hit ratio, the quality of the market timing
matters. (p181)
    - The hit ratio of a prediction-based strategy is only one side of the coin when it comes to
overall strategy performance. The other side is how well the strategy gets the market
timing right. A strategy correctly predicting the best and worst days over a certain period
of time might outperform the market even with a hit ratio below 50%. On the other hand, a
strategy with a hit ratio well above 50% might still underperform the base instrument if it
gets the rare, large movements wrong. (p183)
- Read code - Using machine learning for market movement prediction (p186-202)
    - You have to be careful to not fall into the overfitting trap here. A more realistic picture is
obtained by an approach that uses training data (= in-sample data) for the fitting of the
model and test data (= out-of-sample data) for the evaluation of the strategy
performance. This is done in the following section, when the approach is generalized again
in the form of a Python class. (p199)
    - Applying sophisticated machine learning techniques to stock market prediction often yields
promising results early on. In several examples, the strategies backtested outperform the
base instrument significantly in-sample. Quite often, such stellar performances are due to a
mix of simplifying assumptions and also due to an overfitting of the prediction model. For
example, testing the very same strategy instead of in-sample on an out-of-sample data set
and adding transaction costs—as two ways of getting to a more realistic picture—often
shows that the performance of the considered strategy “suddenly” trails the base
instrument performance-wise or turns to a net loss. (p202)
- Read code - Using deep learning for market movement prediction (p202-217)
    - As an exercise, it is worthwhile to code a Python class (in the spirit of “Linear Regression
Backtesting Class” and “Classification Algorithm Backtesting Class”) that allows for a
more systematic and realistic usage of the Keras package for financial market prediction
and the backtesting of respective trading strategies. (p217)
- The ScikitBacktesterClass can be
used as a starting point to explore more machine learning models and to
apply them to financial time series prediction. (p217)
- Read Python Scripts (p219-226)

## Chapter 6: Building Classes for Event-Based Backtesting (p227)

- On the one hand, vectorized backtesting with NumPy and pandas is generally
convenient and efficient to implement due to the concise code, and it is fast to
execute due to these packages being optimized for such operations. However,
the approach cannot cope with all types of trading strategies nor with all
phenomena that the trading reality presents an algorithmic trader with. When
it comes to vectorized backtesting, potential shortcomings of the approach
are the following: (p227)
    - Look-ahead bias
    - Simplification 
    - Non-recursiveness 
- On the other hand, event-based backtesting allows one to address these
issues by a more realistic approach to model trading realities. On a basic
level, an event is characterized by the arrival of new data. Backtesting a
trading strategy for the Apple Inc. stock based on end-of-day data, an event
would be a new closing price for the Apple stock. It can also be a change in
an interest rate, or the hitting of a stop loss level. Advantages of the event-
based backtesting approach generally are the following: (p228)
    - Incremental approach 
    - Realistic modeling 
    - Path dependency 
    - Reusability 
    - Close to trading 
- Read Backtesting Base Class code (p229-236)
    - Some requirements of class: Retrieving and preparing data, helper nad convenience functions, 
    placing orders, and closing out positions. (p229-230)
    - Using object-oriented programming allows one to build a basic backtesting infrastructure in
the form of a Python class. Standard functionality needed during the backtesting of
different kinds of algorithmic trading strategies is made available by such a class in a non-
redundant, easy-to-maintain fashion. It is also straightforward to enhance the base class to
provide more features by default that might benefit a multitude of other classes built on top
of it. (p236)
- Read code Long-Only Backtesting Class (p236-240)
    - Chapter 5 emphasizes that there are two sides of the performance coin: the hit ratio for the
correct prediction of the market direction and the market timing (that is, when exactly the
prediction is correct). The results shown here illustrate that there is even a “third side”: the
number of trades triggered by a strategy. A strategy that demands a higher frequency of
trades has to bear higher transaction costs that easily eat up an alleged outperformance
over another strategy with no or low transaction costs. Among other things, this often
makes the case for low-cost passive investment strategies based, for example, on
exchange-traded funds (ETFs). (p240)
- Read code Long-Short Backtesting Class (p240-244)
    - To keep the implementation concise throughout, there are many simplifications in the
Python classes that transfer responsibility to the user. For example, the classes do not take
care of whether there is enough liquidity or not to execute a trade. This is an economic
simplification since, in theory, one could assume enough or even unlimited credit for the
algorithmic trader. As another example, certain methods expect that at least one of two
parameters (either units or amount ) is specified. There is no code that catches the case
where both are not set. This is a technical simplification. (p241)
    - Situations where trading might eat up all the initial equity and might even lead to a position
of debt arise, for example, in the context of trading contracts-for-difference (CFDs).
These are highly leveraged products for which the trader only needs to put down, say, 5%
of the position value as the initial margin (when the leverage is 20). If the position value
changes by, say, 10%, the trader might be required to meet a corresponding margin call.
For a long position of 100,000 USD, equity of 5,000 USD is required. If the position drops
to 90,000 USD, the equity is wiped out and the trader must put down 5,000 USD more to
cover the losses. This assumes that no margin stop outs are in place that would close the
position as soon as the remaining equity drops to 0 USD. (p244)
- Read Python Scripts (p246-255)

## Chapter 7: Working with Real-Time Data and Sockets (p256)

- This chapter is about working with real-time data
for which sockets are in general the technological tool of choice. In this
context, here are a few words on central technical terms: Network socket, 
Socket address, Socket protocol, Socket pair, and Socket API. (p256-257)
- http://zeromq.org/ (p257)
- Publisher-subscriber (PUB-SUB) pattern (p257)
- The code in this chapter makes heavy use of ports over which socket communication
takes place and requires the simultaneous execution of two or more scripts at the same
time. It is therefore recommended to execute the codes in this chapter in different terminal
instances, running different Python kernels. The execution within a single Jupyter
Notebook, for instance, does not work in general. What works, however, is the execution
of the tick data server script (“Running a Simple Tick Data Server”) in a terminal and the
retrieval of data in a Jupyter Notebook (“Visualizing Streaming Data with Plotly”). (p258)
- Read code Running a simple tick data server (p258-262)
    - Often, the Monte Carlo simulation of prices for financial instruments relies on
homogeneous time intervals (like “one trading day”). In many cases, this is a “good
enough” approximation when working with, say, end-of-day closing prices over longer
horizons. In the context of intraday tick data, the random arrival of the data is an important
characteristic that needs to be taken into account. The Python script for the tick data
server implements the random arrival times by randomized time intervals during which it
pauses the execution. (p262)
- Read code Connecting a simple tick data client (p262-264)
    - ZeroMQ allows the transmission of other object types, as well. For example, there is an
option to send a Python object via a socket. To this end, the object is, by default, serialized
and deserialized with pickle . The respective methods to accomplish this are
.send_pyobj() and .recv_pyobj() (see The PyZMQ API). In practice, however,
platforms and data providers cater to a diverse set of environments, with Python being only
one out of many languages. Therefore, string-based socket communication is often used,
for example, in combination with standard data formats such as JSON. (p264)
- Read code Signal generation in real time (p264-267)
    - It is a good exercise to implement, based on the presented tick client script, both an SMA-
based strategy and a mean-reversion strategy as an online algorithm. (p267)
- Read code - Visualizing streaming data with Plotly (p268-275)
    - Again, it is a good exercise to combine the plotting of streaming tick data and the two
SMAs with the implementation of an online trading algorithm based on the two SMAs. In
this case, resampling should be added to the implementation since such trading algorithms
are hardly ever based on tick data but rather on bars of fixed length (five seconds, one
minute, etc.). (p271)
- https://bit.ly/zmq_pub_sub (p276)
- http://plot.ly/ (p276)
- https://oreil.ly/7ARrQ (p276)
- Read Python Scripts (p276-280)

## Chapter 8: CFD Trading with Oanda (p281)

- Factors to consider before choosing a broker for algo trading: (p281-282)
    - Instruments 
    - Strategies 
    - Costs 
    - Technology 
    - Jurisdiction 
- http://oanda.com/ (p282)
- http://developer.oanda.com/rest-live-v20/introduction/ (p283)
- https://pypi.org/project/v20/ (p283)
- https://www.investopedia.com/terms/c/contractfordifferences.asp (p285)
- https://github.com/yhilpisch/tpqoa , don't use this instead copy the `tpqoa.py` file from github in local repo
to avoid version issues in future (p286)
- Setting up an account (p286-288)
- Oanda API (p288-290)
    - https://docs.python.org/3/library/configparser.html (p289)
    - The upside of using the configparser module is that it simplifies the storage and
management of account credentials. In algorithmic trading, the number of accounts needed
can quickly grow. Examples are a cloud instance or server, data service provider, online
trading platform, and so on.
The downside is that the account information is stored in the form of plain text, which
represents a considerable security risk, particularly since the information about multiple
accounts is stored in a single file. When moving to production, you should therefore apply,
for example, file encryption methods to keep the credentials safe. (p290)
- Read code Retrieving historical data (p290-297)
    - https://www1.oanda.com/resources/legal/united-states/legal/margin-rules (p295)
    - Leveraged trading does not only amplify potentials profits, but it also amplifies potential
losses. With leveraged trading based on a 10:1 factor (10% margin), a 10% adverse move
in the base instrument already wipes out the complete margin. In other words, a 10%
move leads to a 100% loss. Therefore, you should make sure to fully understand all risks
involved in leveraged trading. You should also make sure to apply appropriate risk
measures, such as stop loss orders, that are in line with your risk profile and appetite. (p296)
- Read code Working with streaming data (p297-298)
- Read code Placing market orders (p298-301)
- Read code Implementing trading strategies in real time (p301-307)
- Read code Retrieving account information (p307-309)
- Read Python Script (p310-312)

## Chapter 9: FX Trading with FXCM (p313)

- Code Getting Started (p315-316)
    - http://fxcmpy.tpq.io/ (p316)
- Read code Retrieving data (p316-322)
- Read code Working with the API (p322-330)
    - Historical data retrieved from the FXCM RESTful API can change with the pricing model
of the account. In particular, the average bid-ask spreads can be higher or lower for
different pricing models offered by FXCM to different groups of traders. (p326)
    - Callback functions are a flexible way to process real-time streaming data based on a
Python function or even multiple such functions. They can be used for simple tasks, such
as the printing of incoming data, or complex tasks, such as generating trading signals based
on online trading algorithms. (p328)
    - By default, FXCM sets up demo accounts as hedge accounts. This means that going long,
say EUR/USD, with 10,000 and going short the same instrument with 10,000 leads to two
different open positions. The default with Oanda are net accounts that net orders and
positions for the same instrument. (p330)

## Chapter 10: Automating Trading Operations (p333)

- Read Capital Management (p334-347)
    - Kelly criterion (p334)
- Read code ML based trading strategy (p347-362)
    - Vectorized backtesting has its limits with regard to how close to market realities strategies
can be tested. For example, it does not allow one to include fixed transaction costs per
trade directly. One could, as an approximation, take a multiple of the average proportional
transaction costs (based on average position sizes) to account indirectly for fixed
transactions costs. However, this would not be precise in general. If a higher degree of
precision is required, other approaches, such as event-based backtesting (see Chapter 6)
with explicit loops over every bar of the price data, need to be applied. (p355)
    - Leverage increases risks associated with trading strategies significantly. Traders should
read the risk disclaimers and regulations carefully. A positive backtesting performance is
also no guarantee whatsoever for future performances. All results shown are illustrative
only and are meant to demonstrate the application of programming and analytics
approaches. In some jurisdictions, such as in Germany, leverage ratios are capped for retail
traders based on different groups of financial instruments. (p357)
- Read code Online Algorithm (p362-369)
- Read Infrastructure and Deployment (p369-370)
    - Although the development and testing of automated algorithmic trading strategies is
possible from a local computer (desktop, notebook, or similar), it is not appropriate for the
deployment of automated strategies trading real money. A simple loss of the web
connection or a brief power outage might bring down the whole algorithm, leaving, for
example, unintended open positions in the portfolio. As another example, it would cause
one to miss out on real-time tick data and end up with corrupted data sets, potentially
leading to wrong signals and unintended trades and positions. (p370)
- Read Logging and Monitoring (p370-373)
    - Trading currency pairs and/or CFDs is associated with a number of financial risks.
Implementing an algorithmic trading strategy for such instruments automatically leads to a
number of additional risks. Among them are flaws in the trading and/or execution logic, as
well as technical risks including problems associated with socket communication, delayed
retrieval, or even loss of tick data during the deployment. Therefore, before one deploys a
trading strategy in automated fashion one should make sure that all associated market,
execution, operational, technical, and other risks have been identified, evaluated, and
properly addressed. The code presented in this chapter is only for technical illustration
purposes. (p373)
- Read Visual step-by-step overview (p373-379)
- Read Python Script (p380-384)

---








