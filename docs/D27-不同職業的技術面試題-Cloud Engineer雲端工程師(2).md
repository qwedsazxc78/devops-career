# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D27-不同職業的技術面試題-Cloud Engineer雲端工程師(2)

## 章節目標

> 快速了解 `雲端產業上中下游的關係` 及代表企業

![D27-不同職業的技術面試題-Cloud Engineer雲端工程師(2)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27.png)

今天的文章專注在Cloud Engineer雲端工程師的第二個問題，來的比較難的 `系統設計` ！

## Q2.【系統設計】設計一個簡單的Web 應用架構，說明如何實現高可用性和擴展性？

* 主考官的目的：測試你對雲端服務設計、配置和系統連結的理解，並提供對應的解決方案，這是一道較具挑戰性的考題。
* 準備方式：系統設計考題較難準備，建議整理過往工作經驗中複雜系統的實例以及經典的雲端架構，列出當時如何執行的方式作為參考。
* 參考標準：設計一個簡單的Web應用架構，可以從單體式架構開始，逐步擴展以實現高可用性，並使用不同的架構元件來達成目標。

### 架構設計與配置

| 架構設計與配置複雜度 | 內容 |
| ---- | ---- |
| 最簡單的單體架構 | - 使用一個虛擬機器來承接流量，內部執行網頁伺服器和資料庫。 <br> - 設定 DNS 與 IP 映射，將流量導向虛擬機器。 |
| 可擴展架構 (流量增加，需要提升整體的流量承受能力) | - 負載均衡器：使用 AWS 的 Elastic Load Balancing (ELB) 分配流量，確保高可用性。<br>  - Web 伺服器：部署多個 Amazon EC2 實例執行 Web 應用，配置自動擴展 (Auto Scaling) 以應對流量變化。 <br> - 資料庫：使用 MySQL 或 PostgreSQL (關聯式資料庫服務) 管理資料。 <br> - 快取：使用 Redis 或 Memcached 來快取資料，減少資料庫壓力。 <br> - 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。 |
| 高可用架構 (進一步考慮區域高可用性與擴展性) | - 負載均衡：ELB 將流量分配到多個可用區域 (AZ) 的 EC2 實例，確保單一 AZ 失效時，流量仍能正常處理。 <br> - 自動擴展：配置自動擴展策略，根據流量增減擴減虛擬機器例數量，確保高峰期穩定執行。考慮使用雲端容器化方案。 <br> - 資料庫高可用性：使用 Amazon RDS 配置主從架構，確保資料高可用性和讀寫分離。 <br> - 水平擴展：使用自動擴展 (Auto Scaling)，根據載量自動擴展或縮減 Web 伺服器數量。 <br> - 快取使用：使用 Redis 或 Memcached 快取熱資料，減少資料庫壓力，設計 TTL 機制與快取資料結構。 <br> - 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。 <br> - CDN：使用 Amazon CloudFront 作為內容傳遞網路，加速全球用戶訪問速度。 |

### 單體架構

![單體架構](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27-1.png)

這是最簡單的架構設計，卻是每個雲端設計第一個學習的架構，適合初始服務

`架構說明` ：
  + 使用一個虛擬機器來承接流量，內部執行網頁伺服器和資料庫。
  + 設定DNS與IP映射，將流量導向虛擬機器。

### 可擴展架構

這是進階的架構設計，隨著初始服務流量增加，需要提升整體的流量承受能力。我們需要針對服務進行水平擴展以及業務分拆。

`架構說明` ：
  + 負載均衡器：使用 AWS 的 Elastic Load Balancing (ELB) 分配流量，確保高可用性。
  + Web 伺服器：部署多個 Amazon EC2 實例執行 Web 應用，配置自動擴展 (Auto Scaling) 以應對流量變化。
  + 資料庫：使用 MySQL 或 PostgreSQL (關聯式資料庫服務) 管理資料。
  + 快取：使用 Redis 或 Memcached 來快取資料，減少資料庫壓力。
  + 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。

![可擴展架構](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27-2.png)

### 高可用架構

這是進階的架構設計，隨著初始服務流量增加，需要提升整體的流量承受能力。我們需要針對服務進行水平擴展以及業務分拆。

`架構說明` ：
  + 負載均衡：ELB 將流量分配到多個可用區域 (AZ) 的EC2實例，確保單一AZ失效時，流量仍能正常處理。
  + 自動擴展：配置自動擴展策略，根據流量增減擴減虛擬機器例數量，確保高峰期穩定執行。考慮使用雲端容器化方案。
  + 資料庫高可用性：使用 Amazon RDS 配置主從架構，確保資料高可用性和讀寫分離。
  + 水平擴展：使用自動擴展 (Auto Scaling)，根據載量自動擴展或縮減 Web 伺服器數量。
  + 快取使用：使用 Redis 或 Memcached 快取熱資料，減少資料庫壓力，設計 TTL 機制與快取資料結構。
  + 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。
  + CDN：使用 Amazon CloudFront 作為內容傳遞網路，加速全球用戶訪問速度。

![高可用架構示意圖](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27-3.png)

## 本日總結

第27天的文章，我們專注於了解 `雲端產業的上中下游` ，台灣雲端產業涵蓋上中下游三個部分。

* 上游：主要是全球知名的雲端服務商，如AWS、Microsoft Azure和Google Cloud，提供全方位的雲端服務，本地也有如中華電信和遠傳等區域雲端供應商。
* 中游：代理商如iKala Cloud、CloudMile和宏庭科技，專門推廣雲端技術，協助企業導入並提供技術支援。
* 下游：則是各行各業的應用廠商，如台積電、統一超商和醫療機構等，利用雲端技術提升營運效率並推動數位轉型。

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
