# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D28-不同職業的技術面試題-System Admin系統管理員-MIS資訊系統工程師(1)

## 章節目標

> 快速了解 `System Admin系統管理員-MIS資訊系統工程師` 技術面試問題與核心能力

![D28-不同職業的技術面試題-System Admin系統管理員-MIS資訊系統工程師(1)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D28.png)

MIS/System Admin系統管理員也是市場相當廣大的工種，這邊提供技術相關面試的內容，這邊也是吃硬底子！今天的文章專注在 `System Admin系統管理員-MIS資訊系統工程師核心能力與基礎知識` 。

作為一名System Admin系統管理員-MIS資訊系統工程師，你需要具備 `資訊系統與網路的基礎知識和實踐經驗` ，以下是這個職位要求的核心能力

## System Admin系統管理員-MIS資訊系統工程師核心能力

* `熟悉操作系統`：能夠操作和管理Linux、Windows、macOS的作業系統。
* `雲端服務知識`：使用過至少一個雲端服務（如AWS、GCP、Azure）的管理控制台，對大部分的服務有基本的認識。
* `權限與安全控制`：針對企業中的資訊系統，能夠實施權限與安全控制以滿足合規要求。
* `系統監控與故障排除`：監控、記錄和排除系統故障，範圍涵蓋雲端與地端伺服器。
* `網路概念應用`：掌握DNS、TCP/IP、防火牆等網路概念，管理企業內部的網路架構。
* `高效能架構設置`：協助設置高可用性、效能和容量要求的高效能架構。
* `業務連續性與災難恢復`：執行業務連續性和災難恢復程序，確保資料和服務的持續性和可恢復性，以及定期的軟體更新。
* `資訊事件管理`：識別、分類和修復突發資訊事件，以及防護可能的資訊安全問題。

## Q1.【基礎知識】請簡述網路架構中OSI七層的差異

* `主考官的目的`：測試你對網路概念的基本理解，因為這是此職位的核心能力之一。
* `準備方式`：基礎知識的準備考驗你對`工作的理解`，建議重點複習計算機概論中的網路部分，這是此職位的必要知識。
* `參考標準`：依據網路運作方式，OSI模型分為七層，每層在網路傳輸中都有不同的功能和作用。理解這些層次之間的差異，可以幫助你更好地設計和管理網路，請參見OSI模型層級說明。

OSI模型層級算是蠻基本的計算機概論考題，但主考官會用更活的方式來確認你是不是懂網路，例如延伸問題一：請問gmail是哪一層網路架構？
更進一步可能會考VPN、SNMP或是FQDN等其他專業的網路名詞，確保你的基礎知識水平，是否能勝任現有工作。

### OSI模型層級說明

| 層級 | 說明 |
| ---- | ---- |
| 1-物理層 (Physical Layer) | - 功能：負責資料的物理傳輸，包括電纜、光纖和無線傳輸介質。 <br> - 範例：纜線、同軸、光纖。確保 1 和 0 的訊號在兩個裝置間正確傳輸。 |
| 2-資料連結層 (Data Link Layer) | - 功能：提供介頁訪問控制和鏈路管理，確保資料的正確傳輸。 <br> - 範例：MAC 位址、交換機。將資料包分解為幀，並在同一網路上的裝置間傳輸。 |
| 3-網路層 (Network Layer) | - 功能：負責資料包的路由選擇和轉發，確保資料到達目的地。 <br> - 範例：路由器、IP 位址。路由傳送資料，例如：使用 ICMP 協定進行 ping 測試。 |
| 4-傳輸層 (Transport Layer) | - 功能：提供端到端的通訊服務，包括可靠的資料傳輸和錯誤檢測。 <br> - 範例：TCP、UDP 協定。TCP 確保資料完整傳輸，UDP 用於視頻等不需要嚴密的應用。 |
| 5-工作階段層 (Session Layer) | - 功能：管理和控制應用之間的通訊會話，確保資料傳輸的有序傳輸。 <br> - 範例：NetBIOS、RPC。建立、管理和終止應用程式之間的會話。 |
| 6-表示層 (Presentation Layer) | - 功能：負責資料的格式化和加密解密，確保資料的兼容性和安全性。 <br> - 範例：加密、壓縮、轉碼。SSL/TLS 協定負責資料加密以保護傳輸安全。 |
| 7-應用層 (Application Layer) | - 功能：提供應用程式間的通訊服務。包括郵件、檔案傳輸和遠程登錄等。 <br> - 範例：HTTP、SMTP、FTP。用戶端軟體如瀏覽器依靠 HTTP 協定進行通訊。 |

## 延伸問題一：請問gmail是哪一層網路架構？

`參考回答` ：Gmail主要運作在 `L7 應用層` ，因為它是一個應用程式，提供電子郵件服務。

## 延伸問題二：請問TCP/UDP 是哪一層網路架構？

`參考回答` ：TCP和UDP是 `L4 傳輸層的協定` ，負責端到端的通訊服務。TCP提供可靠的資料傳輸，而UDP則是不可靠的傳輸協定。

## 本日總結

第28天的文章，我們專注於了解 `不同職業的技術面試題-System Admin系統管理員-MIS資訊系統工程師` 的技術面試，文章中先了解 `System Admin系統管理員-MIS資訊系統工程師核心能力` ，在立刻來個牛刀小試OSI七層架構，驗證你的網路基礎知識。從 `Q1.【基礎知識】請簡述網路架構中OSI七層的差異` 這個問題，可以簡單的知道你是否了解現代網路的基礎概念，網路基礎知識對這份工種是最重要的技能之一。

* 如果文章的技術面試都能夠回答得非常好，恭喜你！你的功力非常深厚，可以持續邁進！
* 如果文章的技術面試沒有太過理解，沒事的，現在開始努力都來得及！繼續看下去提升你的實力！

## 參考資料

1. [AWS的領導力原則（AWS Leadership Principles）](https://www.amazon.jobs/content/en/our-workplace/leadership-principles)
2. [面試必問10大難題懶人包，面試前看這篇就夠！面試官帶你精闢破解](https://www.1111.com.tw/1000w/fanshome/discussTopic.asp?cat=FANS&id=339445)
3. [面試問題詳解！13道常見問題回答技巧及提問，AI面試練習這樣做](https://blog.104.com.tw/top-nine-tricky-interview-questions-and-best-answers/)
4. [內行人才知道的系統設計面試指南](https://www.books.com.tw/products/0010903454)
5. [給全端工程師的職涯生存筆記：從「履歷×面試×職場」打造無可取代的軟實力](https://www.books.com.tw/products/0010928379)
6. [ByteByteGo Newsletter系統架構學習](https://blog.bytebytego.com/p/which-cloud-provider-should-be-used)
7. [AWS Architecture Center](https://aws.amazon.com/architecture/)
8. [GCP Cloud Architecture Center](https://cloud.google.com/architecture)

## 其他連結

* [github: devops-career](https://github.com/qwedsazxc78/devops-career/tree/main)
* [鐵人賽30天章節快速連結目錄](https://ithelp.ithome.com.tw/articles/10351094)

## `有問題歡迎留言，看到立馬解答`
