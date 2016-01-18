# Tumult Hype 3 資料動態實作● 行動裝置動態研究
1. 區塊滑動/手勢
2. 頁面固定上面
3. 捲軸
4. 動態 流暢度
5. 頁面往下拉 會出現搜尋框


##### 版面大小預設為Iphone5 (因個人使用手機版本方便測試)

---



> ### 2016.1.18 



* ##### 行動裝置無法禁止用戶旋轉設備,為了版面顯示正確可使用該裝置尺寸製作適應的版本:

	```
	EX Iphone5:
	Landcape: width: 568px, height: 320px;	
	Portrait: width: 320px, height: 568px;	
	```
 
* ##### 固定動裝置全版面因手勢拖動

	待測試方法1: ` html,body{overflow: hidden} `
	
	待測試方法2: `使用套件AppScroll.js      'AppScroll is a tiny JS library that fixes the "website dragging" issue caused on iDevices' `
	
* ##### 捲軸尺寸css

	```
::-webkit-scrollbar {
    -webkit-appearance: none;
}
::-webkit-scrollbar:vertical {
    width: 6px;
}
::-webkit-scrollbar:horizontal {
    height: 0;
}
::-webkit-scrollbar-thumb {
    background-color: rgba(0, 0, 0, .5);
    border-radius: 10px;
    border: 2px solid #ffffff;
}
::-webkit-scrollbar-track {
    border-radius: 10px;
    background-color: #ffffff;
}

	```


* ##### 滑動區塊顯示/隱藏 

	解決hype拖移事件的方法。可使用於側邊欄、下拉出現收尋框、隱藏按鈕顯示...etc。
