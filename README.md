# Tumult Hype 3 資料動態實作● 行動裝置動態研究

1. 區塊滑動/手勢
2. 頁面固定上面
3. 捲軸
4. 動態 流暢度
5. 頁面往下拉 會出現搜尋框

##### 版面大小預設為Iphone5 (因個人使用手機版本方便測試)

------

- ##### 行動裝置無法禁止用戶旋轉設備
  
  網頁旋轉設備存在BUG
  
  - 方法一: 適應橫屏，將元素全部旋轉90°。(區塊會跟不上旋轉，失敗！)
  - 方法二: 適應橫屏，將元素全部寬度100%展開。( 同樣區塊會跟不上旋轉，失敗！)
  
  總結無論使用所知的何種方法在旋轉設備時，部分區塊會停留在直屏的狀態。
  
 [1/21]

#### 行動裝置無法禁止用戶旋轉設備衍伸出的問題

- 為了固定版面將置頂或置下區塊使用Jquery移動至最外層方法會照成版面適應寬度的問題
  
  解決方法： 取消使用此用法，改變滑動方式。
  
  ​
  
- 使用套件 iScroll 代替滑動效果可讓滑動效果類似app的方式(有ease in out的效果)，已寬高100%適應多數的裝置尺寸。
  
  ​
  
- iScroll套件或有滑動狀態的套件會使hype3.5 viewport的功能無法即時反應，通常要等滑動結束後才會反映動畫。
------


- ##### 固定行動裝置全版面因手勢拖動
  
  測試方法:
  
  ``` tex
  使用套件AppScroll.js
  須將置頂或置下區塊使用Jquery移動至最外層後配合套件使用，
  此動作會將區塊拉出hype框架中會在不同尺寸網頁上會與hype的框架錯開，
  但在固定尺寸設備中是沒問題的。

  ```

  =

- ##### 捲軸尺寸css
  
  ``` css
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


- ##### 滑動區塊顯示/隱藏
  
  使用 snap.js  http://jakiestfu.github.io/Snap.js/demo/apps/default.html
  
  解決hype拖移事件的方法。可使用於側邊欄、下拉出現收尋框、隱藏按鈕顯示...etc。
  
  ​


- ##### 滑動頁面，顯示隱藏元素

  使用hype3.5 Actions中的 Viewport滑動可達到執行元素動畫。
  
  ![snapeGif](https://raw.githubusercontent.com/ChardinXia/Tumult-Hype-3-/master/image/HypeIphone5test.gif)
