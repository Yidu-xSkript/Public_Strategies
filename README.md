![JadeCapital](https://res.cloudinary.com/xplorestate/image/upload/v1668242257/Untitled_design_2_myc9ld.png)
# Public Strategies
These are trading strategies & indicators made public by JadeCapital. The strategy ideas came from different sources.

## ADX-HA+
Average Directional Index where you can select heiken-ashi or the japanese candle type. The purpose of this indicator is to visualize heiken-ashi candle data passed to adx while you're on a standard candle chart 
![ADX-HeikenAshi-Addition](https://res.cloudinary.com/xplorestate/image/upload/v1668242925/Screenshot_2022-11-12_114826_fdfebb.png)
![ADX-HeikenAshi-Addition-Settings](https://res.cloudinary.com/xplorestate/image/upload/v1668243014/Screenshot_2022-11-12_114958_d4kezj.png)

## Half Index
Half Index is a buy/sell signal provider based on the combination of HalfTrend and Laguerre RSI .
The way to trade this is:
    - set an alert on the higher timeframe (30m, 1hr, 4hr, etc.)
    - when an alert is triggered, using the rule of 30, go down to the lower timeframe. example for 30m TF (30*(60/30) => 60sec or 1min)
    - wait for a pullback on the selected lower timeframe (you can use fib retracement tool to see the retracement) or just use the half trend (wait for it to change color from red to green or green to red). You can use whatever method of pullback confirmation you want. 
Added options to view atr channels so that we're able to identify the move after the pullbacks. close < or > the atr channels.
I've also used the fib retracement tool for more confirmation. 
![Half-Index-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668243178/Screenshot_2022-11-12_115248_apyksv.png)
![Half-Index-Settings](https://res.cloudinary.com/xplorestate/image/upload/v1668243201/Screenshot_2022-11-12_115312_w8varh.png)

## Happy Trail
The strategy consists of RSI , HTF stochastic RSI , consolidation range identifier, TSI, and twin range. change the options as you like to see which works for you.

The HTF stochastic retrieves data from any higher timeframe that you've selected and doesn't wait for the candle to close so it repaints. you can disable the option to use this but the strategy looks at the current state of the higher timeframe closed or not if the k is greater than d, at that point you have confirmation to buy and viceversa to sell, so it's your choice if you want to disable it and do it manually.

so basically to buy:
    - HTF stoch rsi - k > d
    - RSI - rsi > rsima (rsima: can be sma , ema , or trama)
    - consolidation zone - if it's in the red zone you don't take the trade
    - TSI - tsi value > signal
    - Twin Range - long trigger signal


To sell:
    - HTF stoch rsi - k < d
    - RSI - rsi < rsima (rsima: can be sma , ema , or trama)
    - consolidation zone - if it's in the red zone you don't take the trade
    - TSI - tsi value < signal
    - Twin Range - short trigger signal

Release Notes: I've added an additional way of filtering out the RSI, by using a linear regression moving average. and another filter called "The Outback" which you can disable. I suggest you to disable it first to test. and I've added an alternative trigger indicator (Trend detection method). I've added a support and resistance identifier to make things easier.
![HappyTrail-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668243743/Screenshot_2022-11-12_120208_qfrrm3.png)

## StairMaster
The strategy consists of RSI (Confirmation), Optional stochastic RSI (Confirmation), consolidation range identifier, Support & Resistance (helps out for beginners), TSV - Time Segmented Volume ( Volume ), A Baseline(has 10 types of moving averages) and Fractal Breakout (Trigger). change the options as you like to see which works for you.

The indicator prints out a sneaker every time the conditions are met. It generally looks for a fractal breakout and at the same time checks for multiple confluences ( RSI , TSV, a Baseline - For Trend direction)

Settings
------------------
Allow Signal Repainting (bool) : Helps if you trade in the lower timeframes to get in quicker.

Stair Sensitivity (int) : changes the fractals sensitivity level
Use Alternate Fractal (bool): Let's you choose a different fractal breakout method

TSV Length (int) : Period (n) of Time segmented volume
TSV MA Length (int) : uses a simple moving average . We use this as a filter. tsvma > 0 and tsv > 0 = buy & tsvma < 0 and tsv < 0 = sell

Baseline Source (source) : Source for the baseline
Baseline Length (int) : Period (n) of the baseline
Baseline Type (string) : there are 10 types of moving average type's you can choose from
Use Baseline as a bias filter (bool) : you'll be able to have a "trend" bias. close > baseline = buy & close < baseline = sell

RSI Length (int) : Period (n) of RSI
RSI Source (source) : Source of the RSI
RSI MA Type (string) : there are 10 types of moving average type's you can choose from
RSI MA Length (int) : Period (n) of RSI ma. We use this as a filter - rsi > rsima = buy & rsi < rsima = sell

Enable stochastic RSI: you can enable filter or disable it. - k > d = buy & k < d = sell
Stochastic RSI is optional

- Consolidation range identifier, support and resistance do not play a part in the signal generating process but they play major roles in the strategy. You can click on "show support & resistance" or "show consolidation zones" to display them on your chart.
- You can also allow sessions in order to know in which session you're trading in. 
![StairMaster-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668243612/Screenshot_2022-11-12_115959_vlhnml.png)

## The Note
The Note is a buy/Sell Signal Providing Indicator with alerts.

Strategy Rules
------------------

    - Setup your alerts wait for a signal on a higher timeframe (eg. 30m, 1hr, 4hr)
    - Go into a lower timeframe (eg. 1m, 5m, 15m - depends on the higher timeframe. 1hr -> 5m, ...) & wait for a pullback - if the pullback goes below the middle ema then the setup is not valid anymore
    - enter once the first coral trend shifts (green to red | red to green) signifying that the market is most likely about to go in your direction.
    - Set your stoploss on the atr band(circle). enable the ATR to display it on your chart.
    - Trade Management - After 2 Fractal BOS's move your SL to breakeven to protect capital.
    - Exit trade when a candle closes below the middle 34 period ema . Set a fixed TP to take partials and let the rest run.

So you obviously know to test this first in a demo account or just backtest it. you can use it if you like. I will not be liable if you lose any capital or blow your accounts or whatever. 
![The-Note-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668243893/Screenshot_2022-11-12_120437_nc0ydo.png)
![The-Note-On-Chart-2](https://res.cloudinary.com/xplorestate/image/upload/v1668244064/Screenshot_2022-11-12_120626_ap71yf.png)

## The Outback
The Outback is a strategy taken from a trading community called "the trading floor". Essentially contains
- RSI, RSI moving average & Hull crossover or crossunder as trigger
- Additional filters like a slow & fast moving averages (multiple types), and ATR Filtering
- optimize the settings to get a good result
![The-Outback-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668244197/Screenshot_2022-11-12_120938_avixqg.png)

## TMA Session
This is Arty's (The Moving Average) strategy on how to trade the 5m TF on a selected session. One trade per day strategy based on the RSI and 3 simple moving averages.
Strategy Rules

   - Draw Support & Resistance or Supply & Demand Zones: Have an understanding of the higher timeframes (1hr TF) - where the structure is and where it's heading.
   - Go into a lower timeframe (5m TF) and wait for a signal (set an alert) on the session you chose. You have the option to view only the first signal or all signals through the session
   - Trade the first signal inside the selected session (Don't trade other signals. if the trade is a loss or win don't trade others after that.)
   - Take TP on fixed 1:2.5 RR or on S&R or S&D Zones
   - Put your SL on the ATR circle
   - There are days you will not find any trades. so don't try to force it. 
![TMASession5m-On-Chart](https://res.cloudinary.com/xplorestate/image/upload/v1668244629/Screenshot_2022-11-12_121655_efvwqw.png)