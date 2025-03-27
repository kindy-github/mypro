import yfinance as yf
# Download historical data for a stock
msft = yf.Ticker("TSLA")
msft_data = msft.history(period="max")
# Display the downloaded data
msft_data.head()




import yfinance as yf
msft = yf.Ticker("TSLA")
msft_data = msft.history(period="max")
tesla_revenue = msft.financials.loc['Total Revenue'].tail(5)
print(tesla_revenue)


import yfinance as yf
msft = yf.Ticker("GME")
gme_data = msft.history(period="max")
GME_revenue = msft.financials.loc['Total Revenue'].tail(5)
print(GME_revenue)



import yfinance as yf
import matplotlib.pyplot as plt

# 下载特斯拉的历史数据
msft = yf.Ticker("TSLA")
msft_data = msft.history(period="max")

# 定义一个函数来绘制图表
def make_graph(data, title):
    plt.figure(figsize=(12, 6))  # 设置图表大小
    plt.plot(data.index, data['Close'], label='Closing Price')  # 绘制收盘价
    plt.title(title)  # 添加标题
    plt.xlabel('Date')  # 添加X轴标签
    plt.ylabel('Price (USD)')  # 添加Y轴标签
    plt.legend()  # 显示图例
    plt.grid(True)  # 添加网格
    plt.show()  # 显示图表

# 使用函数绘制特斯拉股票数据图表
make_graph(msft_data, 'Tesla Stock Price History')



import yfinance as yf
import matplotlib.pyplot as plt
GameStop = yf.Ticker("GameStop")
GameStop_data = msft.history(period="max")

# 定义一个函数来绘制图表
def make_graph(data, title):
    plt.figure(figsize=(12, 6))  # 设置图表大小
    plt.plot(data.index, data['Close'], label='Closing Price')  # 绘制收盘价
    plt.title(title)  # 添加标题
    plt.xlabel('Date')  # 添加X轴标签
    plt.ylabel('Price (USD)')  # 添加Y轴标签
    plt.legend()  # 显示图例
    plt.grid(True)  # 添加网格
    plt.show()  # 显示图表

make_graph( GameStop_data, ' GameStop Stock Price History')
