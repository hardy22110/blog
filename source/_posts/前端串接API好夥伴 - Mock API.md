---
title: 前端串接API好夥伴 - Mock API
date: 2023-01-01 12:04:19
categories:
  - Front-end
tags:
  - 'Tool'
  - 'Mock'
---

# Mock API

![](https://i.imgur.com/dNaZ6oK.jpg)

<div style="text-align: center">
    <a href="https://blog.codecentric.de/mock-service-worker-einfach-backends-mocken">
    原圖取自：Andreas Houben
    </a>
</div>

---

## 情境

- PM : 進度還行嗎？
- Back-end : 水深火熱趕工中，已提供 API 文件給前端
- Front-end : 畫面已切版完成正在串接 API，但很多 API 打不通或有問題需等後端處理
- Tech Lead : 為什麼不使用 Mock API 先串接開發呢？

---

## 前端使用 Mock API 的好處

### 節省前後端開發的時程

原本的工作流程，可能會等後端開發完成後，告訴前端，前端再拿 API 來試試看有沒有規格上的問題或正式開工串接。但這樣的流程前端就必須等待後端。如果用了 Mock API，先定義好雙方溝通的規格後，前後端各自那著這個討論好的規格開發，那就可以雙方同時開工，增進整體時程的效率。

### 前端測試方便度大幅提升

透過 Mock API，前端可以很快速的改變自己需要的資料。更方便的測試前端需要的狀況。EX.透過取得書本列表的 API，當狀態是'Borrowed'，書本列表畫面要是橘色的點；當狀態是'Available'時，書本列表畫面是綠色的點。如果要用真的 API 的話可能就必須要在從後台建立資料，設定不同狀態，但透過 Mock API，只需要複製資料並簡單的修改數值，就可以取得所需的不同狀態資料。

### 降低前端被後端影響的程度

前端在開發的同時，後端也有可能在開發呀！如果後端開發到一半不小心把東西改壞了，或正在調整某個東西這個 API 不能使用，難道前端就要等後端修好才能接著開發嗎？這樣也太被牽制了吧，相信各位前端大大都不喜歡吧 XD 有了 mock API 之後，API response 決定權就會在前端了，各位就不用被後端牽制了，後端大大改壞也可以慢慢修囉～

---

## 建立 Mock API 的流程

### 1. API SPEC 定義完成

- 前後端定義好每隻接口與欄位類型
- 前端知道串接的欄位 Type and Value

### 2. Mock API Request and Response

- 透過輸入 Request 而返回特定的 Response
- 製作各個情境的 Mock 資料

### 3. 區分 API 環境

- 透過設定參數區分各個 API 環境(ex. 正式環境, 開發環境)

### 4. 呼叫 Mock API

- 依據開發或是測試呼叫已建立的 Mock API

---


## Mock API 使用方式

---


## Mock API 注意事項

### API規格未確定時別建立Mock API

### 建置 Mock API 不花太多時間

建置 Mock API 主要是讓前端對於串接 API 與資料可以直接模擬出來產生到畫面上，且可以根據不同情境模擬出不同資料，例如常見的無資料有資料最大資料，
所以花太多時間寫邏輯或是產複雜數據都是本末倒至，應把時間花在串接雨畫面呈現上。

### 呼叫 Mock API 不該與實際上 API 同時呼叫
在功能測試中不要呼叫開發環境API與Mock API，很容易造成Mock數據寫進開發環境中或是造成其他性問題，且真真假假假假真真也很難查出問題。

### 擬真 Mock API 是無法百分之百達到絕對正確
在建立Mock API或是串接API時也是會發生建立錯誤的情況或是與API規格不符合，所以還是會有人工疏失導致最後不正確風險。

---

## Mock API 總結
近年來Mock API工具可以說是讓前端開發流程上有著很大的改變而在導入Mock API也有很多方式與工具但不管哪一種工具也會有相對的優缺點所以也是取決於專案與團隊去選擇，總結來說Mock API可以讓前端可以擁有自己建立的Mock環境，也不會有苦苦等待的問題了。