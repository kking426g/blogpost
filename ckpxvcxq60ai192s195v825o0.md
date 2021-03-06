## 快速增加軟體穩定度的三個方法

身為軟體工程師都知道，在交付功能之前要測試寫出來的程式有沒有符合需求。但當專案隨著時間推移邏輯與功能耦合度越來越高，這時就需要開始思考該如何在開發新功能後仍然維持專案的穩定度。在與多數工程師交流後發現，台灣有在專案中導入測試的公司還是很有限的。因此如果你也遇到了相同得困擾，希望以下的幾個方法能幫助到你。

另外這邊先溫馨提醒，專案穩定性的維持需要投入長期的時間與精神。為提供大家在專案各種情況下都能適用，以下我會分三天跟大家分享以短、中、長期來分析該如何從無到有的規劃。而這中間的關係又分別是什麼。

計畫開始之前我們必須要釐清專案裡有那些關鍵的人物

1. 專案管理者(Project Manager) 或 產品經理(Product Manager)
2. 測試單位(QA Team)
3. 開發單位(Development Team)

這三個單位是最常接觸到專案的角色。如果目前你待的公司缺少任何一種人，那很可能是一人分飾多角的狀況了(為甚麼會有這種情況?! 這邊就不多做討論XD)。接著就要規劃這些單位的合作模式，讓突發狀況的機率降到最低。

今天就來分享在半年內能做什麼來立即改變專案的現況。

### 定期執行影響分析會議(impact analysis meeting)

當PM開出需求後，開發單位應該要進行需求分析並在完成後開影響分析會議。邀請各單位的主要負責人參與，開發者提出修改的範圍與影響區塊，相關單位也可以於會議中釐清可能需要測試的部分。其實會議只是一種執行的方式，你也可以透過信件或是專案管理工具(ex: JIRA)來溝通，主要的目的是為了釐清這次修改的範圍。讓相關單位都能清楚了解需要注意的區塊，有文件參照就能有效減少測試疏漏。網路上有很多相關資源，有興趣的話用impact analysis meeting搜尋就能找到摟。

### 共同建立關鍵測試案例(critical test cases) ，在內部發布時執行

每個產品都有自己最關鍵的功能。舉例來說，如果是購物網站那最重要不外乎是"價錢的正確性"與"購買流程是否能正常執行"。如果測試單位已經有這樣的列表那就太棒了。如果沒有那就必須開會討論出一系列需要被測試的關鍵案例。這些案例需要再每次發布新版本時進行測試，它會是測試單位例行的工作項目之一。有了這些關鍵測試協助，就能有效避免使用者的關鍵行為無法執行，導致需要緊急請工程師修復的情況。
最後，關於測試案例需要注意: 案例需要控制在1 - 2 小時內能處理完，避免影響其他功能進行測試。


### 測試環境與正式同步

測試環境要無限接近或與正式環境一樣。
這點應該很容易理解。但有時也是最容易被遺忘的一環，因為產品可能因為有各種第三方服務的串接，可能沒有提供相對應的測試環境。然而如果因為環境落差造成測試失真，那可以說上面的兩項也是白做工。以網頁開發為例，包含Domain、 API URL、資料、網路路由、CDN快取規則都要一致。

以上就是最快可以開始執行的三個增加產品穩定性的方法。如果你的專案都以經做了這些，但還是很常半夜接到電話起來解issue，那代表需要更長遠的策略。下次再與大家做**如何改善軟體專案穩定性-中期規劃**的分享。



