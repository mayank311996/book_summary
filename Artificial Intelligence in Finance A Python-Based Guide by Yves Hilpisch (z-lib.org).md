# Artificial Intelligence in Finance 

## Preface 

- However, it is safe to say that AI in finance is still at a nascent stage as compared, for example, to industries such as web search or social media. (page ix)
- Table P-1 (page x)
- The book is structured in the following six parts.
	1. Part-1 : The first part discusses central notions and algorithms of AI in general, such as
supervised learning and neural networks (see Chapter 1). It also discusses the
concept of superintelligence, which relates to an AI agent that possesses human-
level intelligence and, in some domains, superhuman-level intelligence (see
Chapter 2). Not every researcher in AI believes that superintelligence is possible
in the foreseeable future. However, the discussion of this idea provides a valuable
framework for discussing AI in general and AI for finance in particular.
	2. Part-2 : The second part consists of four chapters and is about traditional, normative
finance theory (see Chapter 3) and how the field is transformed by data-driven
finance (see Chapter 4) and machine learning (ML) (see Chapter 5). Taken
together, data-driven finance and ML give rise to a model-free, AI-first approach
to finance, as discussed in Chapter 6.
	3. Part-3 : The third part is about discovering statistical inefficiencies in financial markets
by applying deep learning, neural networks, and reinforcement learning. The
part covers dense neural networks (DNNs, see Chapter 7), recurrent neural net‐
works (RNNs, see Chapter 8), and algorithms from reinforcement learning (RL,
see Chapter 9) that in turn often rely on DNNs to represent and approximate the
optimal policy of the AI agent.
    4. Part-4: The fourth part discusses how to exploit statistical inefficiencies through algo‐
rithmic trading. Topics are vectorized backtesting (see Chapter 10), event-based
backtesting and risk management (see Chapter 11), and execution and deploy‐
ment of AI-powered algorithmic trading strategies (see Chapter 12).
    5. Part-5: The fifth part is about the consequences that arise from AI-based competition in
the financial industry (see Chapter 13). It also discusses the possibility of a finan‐
cial singularity, a point in time at which AI agents would dominate all aspects of
finance as we know it. The discussion in this context focuses on artificial finan‐
cial intelligences as trading bots that consistently generate trading profits above
any human or institutional benchmark (see Chapter 14).
    6. Part-6: The Appendix contains Python code for interactive neural network training (see
Appendix A), classes for simple and shallow neural networks that are imple‐
mented from scratch based on plain Python code (see Appendix B), and an
example of how to use convolutional neural networks (CNNs) for financial time
series prediction (see Appendix C).

- One hedge fund based on ML is The Voleon Group, giving return on 9% in 2019 where S&P gave 30%. (page xii)

- This book is only focused on features derived from financial time series. So, no other features are used 
such as sentiments, news, etc. 

- Refer book `Python for Algorithmic Trading: From Idea to Cloud Deploy‐
ment (O’Reilly)` for deployment of strategies presented in this book.

- Other book: `Python for Finance: Mastering Data-Driven Finance (O’Reilly)` [link](https://www.amazon.ca/Python-Finance-Mastering-Data-Driven/dp/1492024333)

## Chapter 1: Artificial Intelligence (page 3)

- Two components of data: features and labels (p4)
- Types of learning: Supervised (eg. whether a debtor is eligible for a loan or not), Unsupervised 
(eg. clustering stocks into certain groups), Reinforcement (p4)
- Unsupervised learning example using KMeans clustering. It can also be used to classify people into 
creditworthy and not creditworthy clusters without using supervised learning. (p5-6)
- Reinforcement learning example (p6-8)
- Types of tasks: estimation and classification (p8)
- Ordinary Least Square function implementation python for degree 1, 2, 3 (p9-13)
- Using neural network to estimate OLS function (p13-16)
- Using poly regression and neural network to estimate on random data (p16-19)
- Classification with neural networks (p20-22)
- Importance of data size on neural network performance (p22-28)
    - Roughly speaking, the neural network, trained on a small data set only, learns wrong
relationships due to the identified two major problem areas. The problems are not
really relevant in the context of learning relationships in-sample. To the contrary, the
smaller a data set is, the more easily in-sample relationships can be learned in general.
However, the problem areas are highly relevant when using the trained neural net‐
work to generate predictions out-of-sample. (means small data is risky)
    - In the context of neural networks that perform prediction tasks, the
volume and variety of the available data used to train the neural
network are decisive for its prediction performance. The numeri‐
cal, hypothetical examples in this section show that the same neural
network trained on a relatively small and not-as-varied data set
underperforms its counterpart trained on a relatively large and var‐
ied data set by more than 10 percentage points. This difference can
be considered huge given that AI practitioners and companies
often fight for improvements as small as a tenth of a percentage
point
- Big data (p28-29)
    - For the purposes of this book, one might say that a big data set is large enough—in terms of vol‐
ume, variety, and also maybe velocity—for an AI algorithm to be trained properly
such that the algorithm performs better at a prediction task as compared to a baseline
algorithm.
- Conclusion (p29)
    - The central theme of this book is the application of neural networks to one of the
core problems in finance: the prediction of future market movements. More specifi‐
cally, the problem might be to predict the direction of movement for a stock index or
the exchange rate for a currency pair. The prediction of the future market direction
(that is, whether a target level or price goes up or down) is a problem that can be
easily cast into a classification setting.

## Chapter 2: Superintelligence (p31)

- This chapter is to pump excitement. Not mandatory at all. Although, covers good concepts 
of RL.
- Table 2-1 for power consumption details on RL algorithms (p43)
- Large hedge funds will push their efforts to generate alpha—a measure for
the out performance of a fund compared to a market benchmark—with AI methods
and agents. Many of them have large dedicated teams working on such efforts (p49)

## Chapter 3: Normative Finance (p61)

- A normative theory is one that is based on assump‐
tions (mathematically, axioms) and derives insights, results, and more from the set of
relevant assumptions. On the other hand, a positive theory is one that is based on
observation, experiments, data, relationships, and the like and describes phenomena
given the insights gained from the available information and the derived results. (p61)
- Uncertainty and risk (p62)
    
`Remaining. Finish later`

## Chapter 4: Data-Driven Finance (p99)

- For the purposes of this
book, data-driven finance is understood to be a financial context (theory, model,
application, and so on) that is primarily driven by and based on insights gained from
data. (p99)
- The scientific method refers to a set of generally accepted principles that should guide
any scientific project. (p100)
    - Expected utility theory (EUT)
    - Mean-variance portfolio (MVP)
    - Capital Asset Pricing Model (CAPM)
    - Arbitrage Pricing Theory (APT)
- [Financial] econometrics is the quantitative application of statistical and mathematical
models using [financial] data to develop financial theories or test existing hypotheses
in finance and to forecast future trends from historical data. It subjects real-world
[financial] data to statistical trials and then compares and contrasts the results against
the [financial] theory or theories being tested. (p101-104)
    - One of the major tools in financial econometrics is regression, in both its univariate
and multivariate forms. (p101)
    - statistical learning. Here, the data is generally given and a functional relationship is to
be found. (p102)
- Data availability (p104-117)
    - Till 2000 people mostly relied on end of the day (EOD) data. (p104)
    - Refinitiv and Bloomberg for data since many years (p104)
    - Programmatic access through APIs is essential and a breakthrough (p104)
    - Read table4-1 (p104)
    - Read Structured historical data code (p105-108) [Data api](https://developers.refinitiv.com/en/api-catalog/eikon/eikon-data-api)
    - Basically all structured financial data is available nowadays in pro‐
grammatic fashion. Financial time series data, in this context, is the
paramount example. However, other structured data types such as
fundamental data are available in the same way, simplifying the
work of quantitative analysts, traders, portfolio managers, and the
like significantly. (p108)
    - Read Structured streaming data code (p108-109) [Data api](http://oanda.com)
    - Most of the financial theories still applied today have their origin in
when EOD data was basically the only type of financial data avail‐
able. Today, financial institutions, and even retail traders and
investors, are confronted with never-ending streams of real-time
data. The example of Apple stock illustrates that for a single stock
during one trading hour, there might be four times as many ticks
coming in as the amount of EOD data accumulated over a period
of 40 years. This not only challenges actors in financial markets,
but also puts into question whether existing financial theories can
be applied to such an environment at all. (p110)
    - Read Unstructured historical data (p110-111) (Again Eikon Data API is used which provides news too)
    - Read Unstructured streaming data. Very important as it covers some NLP applications (p112-113) [Data api](https://professional.dowjones.com/developer-platform/)
    - Read Alternative data code and sources mentioned. There are lot of sources and it is important 
     to select important ones (p113-117)
- Normative theories revisited (p117-143)
    - Standard economic decision theories are intellectually appealing to
many, even to those who, faced with a concrete decision under
uncertainty, would behave in contrast to the theories’ predictions.
On the other hand, big data and model-free, supervised learning
approaches prove useful and successful in practice for predicting
user and customer behavior. In a financial context, this might
imply that one should not really worry about why and how finan‐
cial agents decide the way they decide. One should rather focus on
their indirectly revealed preferences based on features data (new
information) that describes the state of a financial market and
labels data (outcomes) that reflects the impact of the decisions
made by financial agents. This leads to a data-driven instead of a
theory- or model-driven view of decision making in financial mar‐
kets. Financial agents become data-processing organisms that can
be much better modeled, for example, by complex neural networks
than, say, a simple utility function in combination with an assumed
probability distribution. (p122)
    - Read Mean-variance portfolio theory code (p123-130)
    - MVP theory applied to real-world data reveals its practical short‐
comings. Without additional constraints, optimal portfolio compo‐
sitions and rebalancings can be extreme. The predictive power with
regard to portfolio return and Sharpe ratio is pretty bad in the
numerical example, whereas the predictive power with regard to
portfolio risk seems acceptable. However, investors generally are
interested in risk-adjusted performance measures, such as the
Sharpe ratio, and this is the statistic for which MVP theory fails
worst in the example. (p130)
    - Read Capital asset pricing model code (p130-134)
    - The predictive power of the CAPM with regard to the future per‐
formance of stocks, relative to the market portfolio, is pretty low or
even nonexistent for certain stocks. One of the reasons is probably
the fact that the CAPM rests on the same central assumptions as
MVP theory, namely that investors care about only the (expected)
return and (expected) volatility of a portfolio and/or stock. From a
modeling point of view, one can ask whether the single risk factor
is enough to explain variability in stock returns or whether there
might be a nonlinear relationship between a stock’s return and the
market portfolio performance. (p134)
    - Read Arbitrage pricing theory code. This is interesting and can be useful later as 
    it was able to predict market directions correctly (p134-143)
- Debunking central assumptions (p143-155)
    - Previous financial theories might fail in practice due to central assumptions they inherit: normally distributed returns and linear
relationships which is discussed in this section. (p143)
    - Read Normally distributed returns code (p143-152)
    - The first and second moment of a probability distribution only
describe a normal distribution completely. There are infinitely
many other distributions that might share the first two moments
with a normal distribution while being completely different. First moment is mean 
 and second moment is std (p145)
    - Although the normality assumption is a good approximation for
many real-world phenomena, such as in physics, it is not appropri‐
ate and can even be dangerous when it comes to financial returns.
Almost no financial return sample data set passes statistical nor‐
mality tests. Beyond the fact that it has proven useful in other
domains, a major reason why this assumption is found in so many
financial models is that it leads to elegant and relatively simple
mathematical models, calculations, and proofs. (p152)
    - Read Linear relationships code (p153-155)
    - Generally speaking, the higher the beta is, the higher the expected return given a pos‐
itive market performance will be—in a fixed proportional way as given by the beta
value itself. (p153)
    - As with the normality assumptions, linear relationships can often
be observed in the physical world. However, in finance there are
hardly any cases in which variables depend on each other in a
clearly linear way. From a modeling point of view, linear relation‐
ships lead, as does the normality assumption, to elegant and rela‐
tively simple mathematical models, calculations, and proofs. In
addition, the standard tool in financial econometrics, OLS regres‐
sion, is well suited to dealing with linear relationships in data.
These are major reasons why normality and linearity are often
deliberately chosen as convenient building blocks of financial
models and theories. (p155)
- Conclusion (p155)
    - The almost universal and comprehensive
availability of (financial) data has led to a shift in focus from a theory-first approach
to data-driven finance. (p155)
    - Several examples based on real financial data illustrate that
many popular financial models and theories cannot survive a confrontation with
financial market realities. Although elegant, they might be too simplistic to capture
the complexities, changing nature, and nonlinearities of financial markets. (p155)
- Take a look at helper functions code. Useful for some handy NLP tasks (p156-159)

## Chapter 5: Machine Learning (p161)

- Read Data code (p162-165)
- Read Success code (p165-169)
- Read Capacity code (p169-172)
- Read Evaluation code (p172-178)
    - The randomized population of training, validation, and test data
sets is a common and useful technique for data sets that are neither
sequence-like nor temporal in nature. However, when one is deal‐
ing, say, with a financial time series, shuffling the data is generally
to be avoided because it breaks up temporal structures and sneaks
foresight bias into the process by using, for example, later samples
for training and implementing the testing on earlier samples. (p174)
- Read Bias and Variance code (p178-180)
- Read Cross-validation code (p180-182)
    - Overfitting—when a model performs much better on a training
data set than on the validation and test data sets—is to be avoided
in ML in general and in finance in particular. Proper evaluation
procedures and analyses, such as cross-validation, help in prevent‐
ing overfitting and in finding, for example, an adequate model
capacity. (p182)

## Chapter 6: AI-First Finance (p185)

- "If you’re in possession of a function that inputs all the world’s
financial data and outputs the best stocks to buy, you’ll soon be extremely rich". This 
is also a good area to look at, selection of stocks based on multiple features (p185)
- One of the hypotheses with the strongest empirical support is the efficient market
hypothesis (EMH). It is also called the random walk hypothesis (RWH). 1 Simply speak‐
ing, the hypothesis says that the prices of financial instruments at a certain point in
time reflect all available information at this point in time. If the EMH holds true, a
discussion about whether the price of a stock is too high or too low would be point‐
less. The price of a stock, given the EMH, is at all times exactly on its appropriate
level given the available information. (p186)
- Three forms of Efficient Markets (p186)
    - Weak form of EMH
    - Semi-strong form of EMH
    - Strong form of EMH
- Read Efficient markets code (p187-191)
    - Tests for stationarity using the Augmented Dickey-Fuller test (p191)
- Read Market prediction based on returns data code (p192-198)
    - Although the labeling as weak form market efficiency might suggest
otherwise, it is the hardest form in the sense that only time-series-
related data can be used to identify statistical inefficiencies. With
the semi-strong form, any other source of publicly available data
could be added to improve prediction accuracy. (p198)
    - Just analyzing historical return patterns based on OLS regression or
neural networks might not be enough to discover statistical inefficiencies. (p198)
    - There are two major elements of the approach chosen in this section that can be
adjusted in the hope of improving prediction results: 1) In addition to vanilla price-and-returns data, other features can be added to the
data, such as technical indicators (for example, simple moving averages, or SMAs
for short). The hope is, in the technical chartist’s tradition, that such indicators
improve the prediction accuracy. 2) Instead of working with end-of-day data, intraday data might allow for higher
prediction accuracies. Here, the hope is that one is more likely to discover statis‐
tical inefficiencies during the day as compared to at end of day, when all market
participants in general pay the highest attention to making their final trades—by
taking into account all available information. Next section addresses these two (p198)
- Read Market prediction with more features code (p199-203)
    - Basically any traditional technical
indicator used for investing or intraday trading can be used as a
feature to train ML algorithms. In that sense, AI and ML do not
necessarily render such indicators obsolete, rather they can indeed
enrich the ML-driven derivation of trading strategies. (p200)
    - The efficient market hypothesis dates back to the 1960s and 1970s,
periods during which end-of-day data was basically the only avail‐
able time series data. Back in those days (and still today), it could
be assumed that market players paid particularly close attention to
their positions and trades the closer the end of the trading session
came. This might be more true for stocks, say, and a bit less so for
currencies, which are traded in principle around the clock. (p203)
- Read Market prediction intraday code (p204-205)
    - Even if markets are weakly efficient on an end-of-day basis, they can
nevertheless be weakly inefficient intraday. Such statistical ineffi‐
ciencies might result from temporary imbalances, buy or sell pres‐
sures, market overreactions, technically driven buy or sell orders,
and so on. The central question is whether such statistical ineffi‐
ciencies, once discovered, can be exploited profitably via specific
trading strategies. (p205)
- This chapter presents the beginning of the quest to uncover the truth, to discover the
holy grail of finance: proving that markets are not that efficient after all. The relatively
simple neural network approaches of this chapter only rely on time-series-related fea‐
tures for the training. The labels are simple and straightforward: whether the market
(financial instrument’s price) goes up or down. The goal is to discover statistical inef‐
ficiencies in predicting the future market direction. This in turn represents the first
step in exploiting such inefficiencies economically through an implementable trading
strategy (p206)
- Agrawal et al. (2018) explain in detail, with many examples, that predictions them‐
selves are only one side of the coin. Decision and implementation rules that specify in
detail how a certain prediction is dealt with are equally important. The same holds
true in an algorithmic trading context: the signal (prediction) is only the beginning.
The hard part is to optimally execute an appropriate trade, to monitor active trades,
to implement appropriate risk measures—such as stop loss and take profit orders—
and so on. (p206-207)
- One implicit assumption in the approach taken is that
statistical inefficiencies can be discovered based on time-series-related data only. This
is to say that markets are not even weakly efficient—the most difficult form of the
three to disprove. (p207)
- Relying on financial data only and applying general ML and DL algorithms and mod‐
els to it are what this book considers AI-first finance. No theories needed, no model‐
ing of human behavior, no assumptions about distributions or the nature of
relationships—just data and algorithms. In that sense, AI-first finance could also be
labeled theory-free or model-free finance. (p207)
- The major goal of this part is to apply neural networks and reinforcement learning to
discover statistical inefficiencies in financial markets (data). A statistical inefficiency,
for the purposes of this book, is found when a predictor (a model or algorithm in gen‐
eral or a neural network in particular) predicts markets significantly better than a
random predictor assigning equal probability to upwards and downwards move‐
ments. In an algorithmic trading context, to have such a predictor available is a pre‐
requisite for the generation of alpha or above-market returns. (p209)

## Chapter 7: Dense Neural Networks (p211)

- If you’re trying to predict the movements of a stock on the stock market given its
recent price history, you’re unlikely to succeed, because price history doesn’t contain
much predictive information. —François Chollet (2017)
- Read Data code (p212-213)
- Read Baseline Prediction code (p214-218)
- Read Normalization Code (p218-220)
    - The features data is normalized by subtracting the mean of
the training data for every feature and dividing it by the standard deviation of the
training data. This normalization technique is called Gaussian normalization and
proves often, if not always, to be an important aspect when training a neural network. (p218)
- Read Dropout code (p220-222)
    - Dropout in the Sequential model of Keras emulates what all
human beings experience: forgetting previously memorized infor‐
mation. This is accomplished by deactivating certain hidden units
of a hidden layer during training. In effect, this often avoids, to a
larger extent, overfitting a neural network to the training data. (p222)
- Read Regularization code (p222-225)
    - With regularization, large
weights in the neural network get penalized in the calculation of the loss (function).
This avoids the situation where certain connections in the DNN become too strong
and dominant. (p222)
    - Dropout and regularization can be used together. The idea is that the two
measures combined even better avoid overfitting and bring the in-sample and out-of-
sample accuracy values closer together. (p224)
    - Regularization avoids overfitting by penalizing large weights in a
neural network. Single weights cannot get that large enough to
dominate a neural network. The penalties keep weights on a com‐
parable level. (p225)
- Read Bagging code (p225-227)
    - Bagging, in a sense, distributes learning among a number of neural
networks (or other models) in that each neural network, for exam‐
ple, only sees certain parts of the training data set and only a selec‐
tion of the features. This avoids the risk that a single neural
network overfits the complete training data set. The prediction is
based on all selectively trained neural networks together. (p227)
- Read Optimizers code (p227-228)
- The results in
this chapter are promising in that both in-sample and out-of-sample performance—
with regard to the prediction accuracy—are consistently 60% and higher. However,
prediction accuracy is just one side of the coin. An appropriate trading strategy must
be available and implementable to economically profit from the predictions, or
“signals.” This topic of paramount importance in the context of algorithmic trading is
discussed in detail in Part IV. (p228)

## Chapter 8: Recurrent Neural Networks (p229)

- The chapter shows that the application of RNNs to financial time series data can ach‐
ieve a prediction accuracy of well above 60% out-of-sample in the context of direc‐
tional market predictions. However, the results obtained cannot fully keep up with
those seen in Chapter 7. This might come as a surprise, since RNNs are meant to
work well with financial time series data, which is the primary focus of this book. (p230)
- Read First example code (p230-234)
- Read Second example code (p234-237)
    - The first two examples are deliberately chosen to be simple. Both
problems posed in the examples can be solved more efficiently with
OLS regression, for example, by allowing for trigonometric basis
functions in the second example. However, the training of RNNs
for nontrivial sequence data, such as financial time series data, is
basically the same. In such a context, OLS regression, for instance,
can in general not keep up with the capabilities of RNNs. (p237)
- Read Financial price series code (p237-240)
    - The results for the prediction of a financial price series based on an
RNN are in line with the OLS regression approach used in Chap‐
ter 6 to illustrate the EMH. There, it is illustrated that, in a least-
squares sense, today’s price is the best predictor for tomorrow’s
price. The application of an RNN to price data does not yield any
other insight. (p240)
- Read Financial return series code (p240-242)
    - RNN does a good job predicting the direction (p241)
- Read Financial features code (p242-246)
    - The only requirement is that for the nonfinal hidden
layers, the parameter return_sequences is set to True. (p245)
- The out-of-sample prediction accuracy, when predicting market direction, is rela‐
tively high for the classification examples—but it’s not that high and can even be quite
low for the estimation examples. (p247)

## Chapter 9: Reinforcement learning (p249)

`Remaining`

---

`Success means making profits and avoiding losses.
—Martin Zweig`

- Part III is concerned with the discovery of statistical inefficiencies in financial mar‐
kets by the use of deep learning and reinforcement learning techniques. This part, by
contrast, is concerned with identifying and exploiting economic inefficiencies for
which statistical inefficiencies are a prerequisite in general. The tool of choice for
exploiting economic inefficiencies is algorithmic trading, that is, the automated execu‐
tion of trading strategies based on predictions generated by a trading bot. (p279)

- Read tableIV-1 (p279)

- Algorithmic trading is a vast field and encompasses different types
of trading strategies. Some, for example, try to minimize the mar‐
ket impact during the execution of large orders (liquidity
algorithms). Others try to replicate the payoff of derivatives instru‐
ments as closely as possible (dynamic hedging/replication). These
examples illustrate that not all algorithmic trading strategies have
the goal of exploiting economic inefficiencies. For the purposes of
this book, the focus on algorithmic trading strategies that result
from predictions made by a trading bot (for example, in the form
of a DNN agent or an RL agent) seems appropriate and useful. (p280)

---

### Chapter 10: Vectorized Backtesting (p281)

`Big money is made in the stock market by being on the right side of the major moves.
—Martin Zweig`

- The term vectorized backtesting refers to a technical approach to backtesting algorith‐
mic trading strategies, such as those based on a dense neural network (DNN) for
market prediction. (p281)
- Vectorized in this context refers
to a programming paradigm that relies heavily or even exclusively on vectorized code
(that is, code without any looping on the Python level). Vectorization of code is good
practice with such packages such as Numpy or pandas in general and has been used
intensively in previous chapters as well. The benefits of vectorized code are more
concise and easy-to-read code, as well as faster execution in many important scenar‐
ios. On the other hand, it might not be as flexible in backtesting trading strategies as,
for example, event-based backtesting, which is introduced and used in Chapter 11. (p281)
- Having a good AI-powered predictor available that beats a simple baseline predictor
is important but is generally not enough to generate alpha (that is, above-market
returns, possibly adjusted for risk). For example, it is also important for a prediction-
based trading strategy to predict the large market movements correctly and not just
the majority of the (potentially pretty small) market movements. Vectorized backtest‐
ing is an easy and fast way of figuring out the economic potential of a trading
strategy. (p281)
- This chapter focuses on the pure per‐
formance of financial AI agents (trading bots), Chapter 11 goes deeper into risk
assessment and the backtesting of standard risk measures. (p282)
- In all
examples, proportional transaction costs are included in the form of assumed bid-ask
spreads. (p282)
- Read Backtesting an SMA-based strategy code (p282-288)
    - Vectorized backtesting is a powerful and efficient approach to
backtesting the “pure” performance of a prediction-based trading
strategy. It can also accommodate proportional transaction costs,
for instance. However, it is not well suited to including typical risk
management measures, such as (trailing) stop loss orders or take
profit orders. This is addressed in Chapter 11. (p288)
- Read Backtesting a daily DNN-based strategy (p289-295)
    - The DNN-based trading strategy seems promising both before and after typical
transaction costs. However, would a similar strategy be economically viable intraday
as well, when even more trades are observed? The next section analyzes a DNN-based
intraday strategy. (p295)
- Read Backtesting an intraday DNN-based strategy (p295-301)
    - Intraday algorithmic trading in the form discussed in this chapter
often seems appealing from a statistical point of view. Both
in-sample and out-of-sample, the DNN model reaches a high accu‐
racy when predicting the market direction. Excluding transaction
costs, this also translates both in-sample and out-of-sample into a
significant outperformance of the DNN-based strategy when com‐
pared to the passive benchmark investment. However, adding
transaction costs to the mix reduces the performance of the DNN-
based strategy considerably, making it unviable for typical retail
bid-ask spreads and not really attractive for lower, high-volume
bid-ask spreads. (p301)
- Vectorized backtesting proves to be an efficient and valuable approach for backtesting
the performance of AI-powered algorithmic trading strategies. This chapter first
explains the basic idea behind the approach based on a simple example using two
SMAs to derive signals. This allows for a simple visualization of the strategy and
resulting positions. It then proceeds by backtesting a DNN-based trading strategy, as
discussed in detail in Chapter 7, in combination with EOD data. Both before and
after transaction costs, the statistical inefficiencies as discovered in Chapter 7 translate
into economic inefficiencies, which means profitable trading strategies. When using
the same vectorized backtesting approaches with intraday data, the DNN strategy also
shows a significant outperformance both in- and out-of-sample when compared
to the passive benchmark investment—at least before transaction costs. Adding trans‐
action costs to the backtesting illustrates that these must be pretty low, on a level
often not even achieved by big professional traders, to render the trading strategy
economically viable. (p301)

## Chapter 11: Risk Management (p303)

- Vectorized backtesting in general enables one to judge the economic potential of a
prediction-based algorithmic trading strategy on an as-is basis (that is, in its pure
form). Most AI agents applied in practice have more components than just the
prediction model. (p303)
- In a financial context, AI agents or trading bots are also not deployed as-is in general.
Rather, there are a number of standard risk measures that are typically used, such as
(trailing) stop loss orders or take profit orders. The reasoning is clear. When placing
directional bets in financial markets, too-large losses are to be avoided. Similarly,
when a certain profit level is reached, the success is to be protected by early close
outs. How such risk measures are handled is a matter, more often than not, of human
judgment, supported probably by a formal analysis of relevant data and statistics.
Conceptually, this is a major point discussed in the book by Agrawal et al. (2018): AI
provides improved predictions, but human judgment still plays a role in setting deci‐
sion rules and action boundaries. (p303)
- This chapter has a threefold purpose. First, it backtests in both vectorized and event-
based fashion algorithmic trading strategies that result from a trained deep
Q-learning agent. Henceforth, such agents are called trading bots. Second, it assesses
risks related to the financial instrument on which the strategies are implemented.
And third, it backtests typical risk measures, such as stop loss orders, using the event-
based approach introduced in this chapter. The major benefit of event-based
backtesting when compared to vectorized backtesting is a higher degree of flexibility
in modeling and analyzing decision rules and risk management measures. In other
words, it allows one to zoom in on details that are pushed toward the background
when working with vectorized programming approaches. (p304)


