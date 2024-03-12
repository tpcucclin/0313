Github Copilot - [官網: Quickstart for GitHub Copilot](https://docs.github.com/en/copilot/quickstart)
---

#### VS Code 外掛套件
- 必裝參考指南  [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview#_chat-view)
- Youtube 教學 [How To Use GitHub Copilot (with Python Examples)](https://www.youtube.com/watch?v=tG8PPne7ef0)
- Youtube 教學 [GitHub Copilot for Python Development](https://www.youtube.com/watch?v=wNsiJWewyjU)
- Youtube 教學 [Get Started with the Future of Coding: GitHub Copilot](https://www.youtube.com/watch?v=Fi3AJZZregI)


一、準備工作
---

### 1、帳號註冊

> 需要先擁有一個Github帳號，訂閱Copilot。

事項 | 說明
:-|-
Github 帳號 | [註冊網址](https://github.com/signup)
訂閱 Github Copilot | [訂閱網址](https://github.com/features/copilot)

### 2、安裝Vscode套件


> 在擴充商店中搜尋安裝下面套件

套件名稱 | 功能
:-|-
`GitHub Copilot`|編輯器中進行程式碼補全提示
`GitHub Copilot Chat`|套件列可以與copilot對話

### 3、Vscode 中登入 Github 帳號

- 安裝後，點擊右下角的 `GitHub Copilot` 插件圖標，然後點擊 `Sign in to GitHub` 登入。
- 或者，點擊工具列中的 `Accounts` 圖標，然後點擊 `使用 Github 登陸以使用Github Copilot` 進行登入。

### 4、Copilot 訂閱方案 - [官網: About billing for GitHub Copilot](https://docs.github.com/en/billing/managing-billing-for-github-copilot/about-billing-for-github-copilot)
方案 | 價格 | 特性
:-|-|-
Copilot Individual | 10美元/人/月，100美元/人/年 <br>If you choose a monthly billing cycle, you will be billed $10 USD per calendar month. If you choose a yearly billing cycle, you will be billed $100 USD per year. <br> (學生, 教師, 開源專案貢獻者 免費) | 程式碼補全, 聊天機器人
Copilot Business| 19美元/人/月 |程式碼補全, 聊天機器人, 命令列工具, 安全漏洞篩選, 程式碼參考, 公共程式碼篩選, 智慧財產權, 企業安全與隱私保障
Copilot Enterprise| 39美元/人/月 | Business 特性 + 私人代碼庫的個人化聊天 + 文件搜尋總結 + Git Pull Request 摘要 + 程式碼審查 + 模型微調

[Quickstart for GitHub Educators](https://docs.github.com/en/education/quickstart)
---
Tip: If you're a student and you'd like to take advantage of an academic discount, see "[Apply to GitHub Global Campus as a student.](https://docs.github.com/en/education/explore-the-benefits-of-teaching-and-learning-with-github-education/github-global-campus-for-students/apply-to-github-global-campus-as-a-student)"

Requirements

- To be eligible for GitHub Global Campus, including GitHub Student Developer Pack and other benefits, you must:
- Be currently enrolled in a degree or diploma granting course of study such as a high school, secondary school, college, university, homeschool, or similar educational institution
- Have a verifiable school-issued email address or upload documents that prove your current student status
- Have a GitHub personal account
- Be at least 13 years old

### 提示技巧
<!--rehype:wrap-class=col-span-1 row-span-1-->

1. 提供上下文信息
2. 上下文可被預測

實戰教學
---
- [Youtube GitHub Copilot Series](https://www.youtube.com/playlist?list=PLj6YeMhvp2S5_hvBl2SE-7YCHYlLQ0bPt)
- [Pragmatic techniques to get the most out of GitHub Copilot](https://www.youtube.com/watch?v=CwAzIpc4AnA)
- [How I used GitHub Copilot to build a browser extension](https://github.blog/2023-05-12-how-i-used-github-copilot-to-build-a-browser-extension/)

上下文：文件
---
> Copilot會查看編輯器中目前和緊鄰開啟的文件，以分析上下文並提供適當的建議。

---

> - 1、避免開啟過多的文件，讓Copilot更能理解你的程式碼。
> - 2、開啟的文件盡量相關且有共通點。
> - 3、如果是新項目，可以開啟一些模版程式碼、資料檔案以及參考文件等相關範例文件。 以便Copilot更能理解你的期望。 等已經開發了一些程式碼後，這些範例檔案就可以刪除了。

上下文: 註解(頂部註解)
---
建立一個新文件時，在文件頂部添加註解，描述你的需求。 這對 Copilot 很有幫助。

- 以下說明將使用`...`表示copilot開始產生的位置

```python
# Download file from an URL and analyze its content
# Details:
# * Download the file from an URL
# * Save the downloaded files into `./download` folder
# * Use `filetype` of the file to specify how to parse
# * Filetype can be `.pdf`, `.html`, `.epub`, `.md` and `.txt`
# * Use NLP or OCR to get the file content
# * Tokenize the file content and get the statistics result

import ...
```

---
```Python
#給你二個向量 A(x1 , x2 , x3 )、B(y1 , y2 , y3 ) 請輸出他們的內積。
#Input File Format
#每筆輸入檔案包含二列,分別代表向量 A(x1 , x2 , x3 ) 與向量 B(y1 , y2 , y3 )。
#Output Format
#輸出內積值(x1 ∗ y1 + x2 ∗ y2 + x3 ∗ y3 )

# Read the input file
with open("input.txt", "r") as file:
    lines = file.readlines()

# Extract the vector values
vector_A = list(map(int, lines[0].split()))
vector_B = list(map(int, lines[1].split()))

# Calculate the dot product
dot_product = sum(a * b for a, b in zip(vector_A, vector_B))

# Print the dot product
print(dot_product)
```

上下文: 註解(行內註解)
---

在每個函數上方或重要程式碼區塊的上方加入註解，以幫助 Copilot 了解你程式碼中的一些意圖或問題。

- 以下說明將使用`...`表示copilot開始產生的位置

函數上方新增註解說明
```
# parse the JSON string into User object
def ...
```
或是

```python
# Create a list of 100 numbers
# 產生 100 個數字的列表
numbers = [i for i in range(1, 101)]
# Create a list of 100 numbers, but only the even numbers
# 產生 100 個數字的列表，但只有偶數
numbers = [i for i in range(1, 101) if i % 2 == 0]
 
```

或是

```python
# 將 a="1 2 3" 的字串轉換成整數串列 [1, 2, 3]
...
# 以下是自動生成之程式碼
a = "1 2 3"
a_list = list(map(int, a.split()))
```

上下文: 註解(QA提問)
---
> 如果你不想切換到 copilot chat 時，註解也可以用來提問。
```
# Q: 什麼是 dict 型態
# A: dict 是一種 key-value pair 的資料結構，可以用來儲存任意數量的資料，並且可以用 key 來取得 value
```

---
Github Copilot  Chat

- Ctrl+I 以要求 Github Copilot Chat 執行某些動作

請給一個  bash 程式完成下列需求
1. 接受一個參數 x 
2. 判斷如果 x 內容為 "apple" 則顯示 "蘋果"
3. 判斷如果 x 內容為 "banana" 則顯示 "香蕉"
4. 如果沒給參數，則顯示 "請提供水果名稱"

```bash
#!/bin/bash

if [ -z "$1" ]; then
    echo "請提供水果名稱"
elif [ "$1" = "apple" ]; then
    echo "蘋果"
elif [ "$1" = "banana" ]; then
    echo "香蕉"
fi
```


```
快捷鍵
如果已經有 copilot 可以使用的人，這些快捷鍵可以幫助你省下更多時間：

alt + \ : 跳出建議，通常換行的時候就會有建議，但如果不小心弄掉，可以用此快速鍵重新叫出來
alt+[ , alt+] : 覺得這個建議不好，可以切換不同建議
ctrl + enter : 跳出 copilot 視窗，最多會顯示十筆建議
tab : 看到建議的當下如果滿意，就直接 tab 使用此建議
```

