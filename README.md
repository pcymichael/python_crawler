# Python_crawler :bug:
<p align="center">
    <a href="">
        <img src="https://img.shields.io/badge/未完-間斷性更新-brightgreen">
    </a>
    <a href="">
        <img src="https://img.shields.io/badge/Python-3.8-9cf">
    </a>
</p>

一些簡單基本的爬蟲例子，新手好學習，會把一些練習過的 code 丟在這，下面會做一些簡單的介紹
    
> Finish：
> 1. Goosping information
> 2. Beauty image
> 3. Instagram image ([Note](https://hackmd.io/@RsJen3MIQR6hHHZ68uAsoA/HkExCi83L))
> 4. Google search Weather
> 5. Google search 
> 5. Air quality
    
> Trying：
> 1. Dcard image
> 2. Oil price
> 3. Pixiv daily image
> 4. Anime info

# Setup
會使用到的套件
```
pip install requests
pip install beautifulsoup4
```

# Requests
Requests 是一個 Python HTTP 庫，HTTP 是一種請求/回應式的網路協定
就像你要連上一個網站時，你一定是先輸入網址，然後請求伺服器，伺服器就會回應資料給你

範例
```python
import requests
response = requests.get('https://www.ptt.cc/bbs/Gossiping/index.html')
```

# Methods
共有8種：GET、HEAD、POST、PUT、DELETE、TRACE、OPTIONS 和 CONNECT

爬蟲，通常只需要用到 GET 和 POST 方法

## Get
向指定的資源要求資料，類似於查詢操作

練習網址：```http://pythonscraping.com/pages/page1.html```

## POST
將要處理的資料提交給指定的資源，類似於更新操作

練習網址：```http://pythonscraping.com/pages/files/form.html```

## Status Code
回應永遠是一個十進位的三位數數字，代表一種 response 的狀態
- 1xx 系列是資訊回應
- 2xx 系列是成功回應
- 3xx 系列是重新導向
- 4xx 系列是客戶端錯誤
- 5xx 系列是伺服器端錯誤

比較常見的大概是 200，表示成功
404 表示沒有這個網頁，或者已移除
403 表示沒有權限存取等等

# BeautifulSoup find tag
```
# 取得第一個(h4)，以下寫法皆相同：
print(soup.find('h4'))
print(soup.h4)

# 以下寫法皆相同：
soup.find_all('h4', 'title')
soup.find_all('h4', {'class': 'title'})
soup.find_all('h4', class_='title')

# 當 key 含特殊字元時, 使用 dict 取得元件
print(soup.find(data-foo='mac-foo'))  # 會導致 SyntaxError
print(soup.find('', {'data-foo': 'mac-foo'}))
```

# 其他紀錄
> Google search URL：https://www.google.com/search?q=TPE+2330&hl=zh-TW