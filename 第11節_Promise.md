### 第11節 Promise  

81. 為什麼需要 Promise  
- 為什麼需要 Promise  
  Promise 是用來處理非同步  
  Ajax 是用來處理遠端資料  
   
- Promise 很常用來處理 Ajax 的行為  
  除了 Ajax 以外, 其他非同步行為, 也很適合用 Promise 來做處理  

- 先介紹 Ajax  
  載入兩個套件  
  一個是 jQuery, 使用到 Ajax 的方法  
  一個是 axios, 是基於 Promise 的遠端請求工具  

- 到 jQuery 官網, 輸入 ajax. 到了 jQery.ajax();  
  可以看到他有哪些方法, 遠端的請求有很多方法  
  [jQery.ajax](https://api.jquery.com/jquery.ajax/#jQuery-ajax-url-settings)

- 看一下 randomuser 的網站  
  可以對一個網址發出請求, 他會回傳一個 json  
  [randomuser](https://randomuser.me/api)    
  
- 例1~2: 例１跟 例 2, 兩者的執行結果相同, 但兩者結構完全不同  
[sandbox](https://codesandbox.io/s/81-weishimoxuyao-promise-li-1-nf7mb?file=/index.html)  

- 例3: 非同步行為, 會等其他程式碼執行完, 才執行  
(情3)試著在 ajax 執行兩次, 寫法會越來越巢  
[randomuser document seeds](https://randomuser.me/documentation#seeds)  
[sandbox](https://codesandbox.io/s/81weishimoxuyao-promise-li-3-fo51s?file=/index.html:1403-1425)  

- 常見的非同步問題(不限於 Ajax)  
  1. 回呼地獄  
     如例3-情3 巢狀結果會越來越嚴重  
  2. 寫法不一致  
     ajax 可以寫 done, 也可以寫 success,  
     這兩種寫法就不一樣, 如果再加上其他非 promise 基礎的套件  
    他的寫法可能也會不一樣  
  3. 無法同時執行  
     -jQuery 有並行寫法, 但不直覺   
     -非同步行為在執行的時候, 不能確保哪個時間作開始,  
     哪個時間做結束,   
     -在 ajax 若請求需要同時發出, 且確保所有行為完成之後,   
     再進行一下個步驟的話, 那麼許多非 promise 為基礎的套件, 就沒辦法做到  
     - Promise 有固定寫法, 來同時發送請求,  
     並且所有請求完成後, 才會做下一個動作   

- axios, 到github 上看 getm post 
  [axios github](https://github.com/axios/axios)  
  
- 例4 例5  
[sandbox](https://codesandbox.io/s/81weishimoxuyao-promise-li-4-li5-8jsup?file=/index.html:1081-1409)
```
// 例 4
// 說明 １
// 遠端請求完成, 就會用 then 做串接
// 所有 promise 都是用 then 做串接
// 改善寫法不一致的問題

// 說明 ２
// 使用串接的語法, 避免回呼地獄

// 例 5
// Promise.all([]) 透過陣列, 同時發送請求, 並確保完成
// 才執行它的結果(解決問題三)
```

82. Promise 基礎概念  

83. 創立自己的 Promise  
 
84. 鏈接技巧  

85. Promise 常用方法  

86. Promise 與 Ajax   






