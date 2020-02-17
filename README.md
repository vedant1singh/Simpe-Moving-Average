# Simpe-Moving-Average

import pandas as pd
import matplotlib.pyplot as plt
import quand1
auth_token = open("alt.text", "r")
def SMA(data, ndays):
    SMA = pd.Series(pd.rolling_mean(data['Close'], n), name = 'SMA')
    data = data.join(SMA)
    return data

data = quand1.get('MCX/GYD2018', start = '2018-03-03', end ='2020-09-12')
data = pd.DataFrame(data)

n = 9
SMG = SMA(data, n)
SMA = SMG['SMA']
print(SMG)
SMG.plot()
plt.show
