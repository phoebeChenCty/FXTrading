# api
login through www.oanda.com/demo-account

e1f7980a69a2fb459301e79beb73433b-257c9fa8b70bd768ec1edb63cae54240

v20 Account Number 101-001-25150540-001

## develop guide
https://developer.oanda.com/rest-live-v20/development-guide/

url: 	https://api-fxpractice.oanda.com


# postman
rapid api instead

# set jupyter theme
jt -t onedork -f roboto -cellw 95%

# step
oanda_api.py
main.py
defs.py

instrument.py

instrument_collection.py

plotting.py

ma_cross.py


# backtesting
load candle data

calculate indicator, i.e. RSI, EMA
check candle patterns

create a slimer dataframe using only useful columns

determine buy and sell signal
determine take profit and stop loss

plot candles and indicators and buy & sell signal to check if it looks correct

simulate trading and gain

# pandas
    typical_p = ( df.mid_c + df.mid_h + df.mid_l ) / 3
    stddev = typical_p.rolling(window=n).std()
    df['BB_MA'] = typical_p.rolling(window=n).mean()
    prev_c = df.mid_c.shift(1)
    tr = pd.DataFrame({'tr1': tr1, 'tr2': tr2, 'tr3': tr3}).max(axis=1)
    df['EMA'] = df.mid_c.ewm(span=n_ema, min_periods=n_ema).mean()
    c_atr = f"ATR_{n_atr}"
    df.drop(c_atr, axis=1, inplace=True)
    gains = df.mid_c.diff()
    wins = pd.Series([ x if x >= 0 else 0.0 for x in gains ], name="wins")
    body_lower = df_an[['mid_c','mid_o']].min(axis=1)
    low_change = df_an.mid_l.pct_change() * 100
    df_an['SHOOTING_STAR'] = df_an.apply(apply_shooting_star, axis=1)
    for index, row in df.iterrows():
    for index in range(df.shape[0]):
        val1 = df.mid_c.iloc[index] * 12
    ar1 = df.mid_c.array
    for index in range(ar1.shape[0]):
        val1 = ar1[index] * 12
    df.dropna(inplace=True)
    df_trades.fillna(0, inplace=True)
    df.to_pickle(filename)
    df = pd.DataFrame.from_dict(rl)
    df = pd.concat([x.df_trades for x in results_list])
    df_signals = df[df.SIGNAL != NONE].copy() 
    df_signals['m5_start'] = [x + dt.timedelta(hours=time_d) for x in df_signals.time]
    df.reset_index(drop=True, inplace=True)    
    df_signals.drop(['time', 'mid_o', 'mid_h', 'mid_l', 'bid_o', 'bid_h', 'bid_l',
    'ask_o', 'ask_h', 'ask_l', 'direction'], axis=1, inplace=True)
    df_signals.rename(columns={
        'bid_c' : 'start_price_BUY',
        'ask_c' : 'start_price_SELL',
        'm5_start' : 'time'
    }, inplace=True)
    df_m5_slim = self.df_m5[['time','bid_h', 'bid_l', 'ask_h', 'ask_l' ]].copy()
    self.merged = pd.merge(left=df_m5_slim, right=df_signals, on='time', how='left')
    df = pd.read_pickle(f"./data/{pair}_H{time_d}.pkl")
    final_df.drop_duplicates(subset=['time'], inplace=True)
    final_df.sort_values(by='time', inplace=True)
  
