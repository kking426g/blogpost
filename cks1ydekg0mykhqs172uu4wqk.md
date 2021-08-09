## 如何於Microsoft Teams建立Gitlab repository行為推播機器人

Microsoft Teams 是近年來在商務上知名的產品。越來越多公司廢棄 Skype 轉而使用Teams。改用 Teams 後發現他提供了很多工具，能幫助工程師在完成專案的過程中更方便的管理專案與工作。今天要來跟大家簡單分享如何將gitlab的專案行為利用Teams提供的第三方工具來建置自動推播機器人。

### 於 Teams 建立 Gitlab通知團隊
我會特別建一個團隊專門放置gitlab的行為通知，因為當多人在同個repo上開發，大家commit很頻繁的時候如果使用專案用的頻道容易造成洗版。建議大家如果有相同狀況可以照以下方式建立新的Teams團隊。
* 點擊團隊
* 在下方選擇 ``建立團隊``
* 選擇 ``建立一個團隊``
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628347932300/JvfW4hxim.png)

### 於Teams 建立 Incoming Webhook
接下來需要到Teams中建立webhook才能接收Gitlab傳進來的通知。
* 點擊 Teams 內的 ``應用程式`` 功能
* 在搜尋列打上 Incoming Webhook
* 選擇下圖綠色框的項目
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628347252534/NMiWwKmLb.png)


### 綁定Incoming Webhook至已建立的團隊
* 點擊 ``新增至團隊``
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628348637746/H2ZoiRUEh.png)

* 選定團隊名稱並設定連接器
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628348599484/X-IdYtOI5.png)


* 建立此webhook的名稱。這邊建議寫該專案的名稱，因為這會顯示在每次通知的旁邊
* 編輯通知時的圖像
* 點選``建立``
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628349033839/TvTm2ep-f.png)


* 點選建立後，會出現下方URL欄位，copy此url。

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628516642928/LCESEP5Mg.png)

恭喜你! 以上就已經完成Teams的基本設置。接下來我們要透過Teams複製的URL到Gitlab的專案中進行設定。

### 至Gitlab專案中進行設定
一、 使用 [Administrator](https://docs.gitlab.com/ee/user/permissions.html) 權限登入要進行設定的專案中  
二、 選擇 ``Settings > Integtations``  
三、 選擇 ``Microsoft Teams notifictions``

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628350312260/qPsJ4Oy94.png)

四、在Enable的區塊勾選Active  
五、 選擇想要通知的行為，有以下幾種


- Push
- Issue
- Confidential issue
- Merge request
- Note
- Confidential note
- Tag push
- Pipeline - If you enable this trigger, you can also select Notify only broken pipelines to be notified only about failed pipelines.
- Wiki page

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628350498359/rd7LH1Izy.png)


六、最下方有Webhook欄位，貼上剛才在Teams複製好的URL  
七、進行測試並儲存
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1628350786185/V7I4n3cya.png)


以上就已經完成了所有的設定，Gitlab會透過 Teams 提供的URL將通知推播至團隊中。這樣以後就可以知道團隊裡大家的開發進度啦。

[gitlab官方參考連結](https://docs.gitlab.com/ee/user/project/integrations/microsoft_teams.html
)