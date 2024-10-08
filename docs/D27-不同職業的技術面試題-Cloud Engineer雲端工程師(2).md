# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D27-不同職業的技術面試題-Cloud Engineer雲端工程師(2)

## 章節目標

> 快速了解 `Cloud Engineer雲端工程師` 技術面試問題與核心能力

![D27-不同職業的技術面試題-Cloud Engineer雲端工程師(2)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27.png)

今天的文章專注在Cloud Engineer雲端工程師的第二個問題，來到比較難的 `系統設計` ！

## Q2.【系統設計】設計一個簡單的Web應用架構，說明如何實現高可用性和擴展性？

* `主考官的目的`：測試你對雲端服務設計、配置和系統連結的理解，並提供對應的解決方案，這是一道較具挑戰性的考題。
* `準備方式`：系統設計考題較難準備，建議整理過往工作經驗中複雜系統的實例以及經典的雲端架構，列出當時如何執行的方式作為參考。
* `參考標準`：設計一個簡單的Web應用架構，可以從單體式架構開始，逐步擴展以實現高可用性，並使用不同的架構元件來達成目標。

### 單體架構

這是最簡單的架構設計，卻是每個雲端設計第一個學習的架構，適合初始服務

`架構說明` ：
  + 使用一個虛擬機器來承接流量，內部執行網頁伺服器和資料庫。
  + 設定DNS與IP映射，將流量導向虛擬機器。

![單體架構](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D27-1.png)

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

### 架構設計與配置

| 架構設計與配置複雜度 | 內容 |
| ---- | ---- |
| 最簡單的單體架構 | - 使用一個虛擬機器來承接流量，內部執行網頁伺服器和資料庫。 <br> - 設定 DNS 與 IP 映射，將流量導向虛擬機器。 |
| 可擴展架構 (流量增加，需要提升整體的流量承受能力) | - 負載均衡器：使用 AWS 的 Elastic Load Balancing (ELB) 分配流量，確保高可用性。<br>  - Web 伺服器：部署多個 Amazon EC2 實例執行 Web 應用，配置自動擴展 (Auto Scaling) 以應對流量變化。 <br> - 資料庫：使用 MySQL 或 PostgreSQL (關聯式資料庫服務) 管理資料。 <br> - 快取：使用 Redis 或 Memcached 來快取資料，減少資料庫壓力。 <br> - 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。 |
| 高可用架構 (進一步考慮區域高可用性與擴展性) | - 負載均衡：ELB 將流量分配到多個可用區域 (AZ) 的 EC2 實例，確保單一 AZ 失效時，流量仍能正常處理。 <br> - 自動擴展：配置自動擴展策略，根據流量增減擴減虛擬機器例數量，確保高峰期穩定執行。考慮使用雲端容器化方案。 <br> - 資料庫高可用性：使用 Amazon RDS 配置主從架構，確保資料高可用性和讀寫分離。 <br> - 水平擴展：使用自動擴展 (Auto Scaling)，根據載量自動擴展或縮減 Web 伺服器數量。 <br> - 快取使用：使用 Redis 或 Memcached 快取熱資料，減少資料庫壓力，設計 TTL 機制與快取資料結構。 <br> - 儲存：使用 Amazon S3 儲存靜態資源，確保高可用性和可擴展性。 <br> - CDN：使用 Amazon CloudFront 作為內容傳遞網路，加速全球用戶訪問速度。 |

## 本日總結

第27天的文章，我們專注於了解 `Q2.【系統設計】設計一個簡單的Web 應用架構，說明如何實現高可用性和擴展性？` ，系統設計比較硬喔，不是可以輕鬆寫意的回答出來的，需要深厚的功力。系統設計問題，可以知道你是否了解現代流行的雲端架構系統，並根據業務邏輯來進行系統設計。這種問題真得是台上10分鐘，台下10年功，用ChatGPT也不是能夠輕易回答的喔！

* 如果文章的技術面試都能夠回答得非常好，恭喜你！你的功力非常深厚，可以持續邁進！
* 如果文章的技術面試沒有太過理解，沒事的，現在開始努力都來得及！繼續看下去提升你的實力！

雲端工程師的技術面試，會針對在雲端基礎設施的認識與使用，如同前面說明的核心能力。最後再藉由工作經驗的提升，逐漸在往DevOps/SRE等進階工種邁進，但也是需要更多的知識積累。

* `雲端服務知識`：熟悉至少一個主要雲端服務平台（如AWS、GCP、Azure）的管理控制台和核心服務（如計算、儲存、網路、資料庫）。
* `操作系統管理`：能夠操作和管理Linux、Windows等作業系統，進行雲端虛擬系統的安裝、配置、管理和故障排除。
* `權限與安全控制`：實施並管理雲端環境中的身分和訪問管理（IAM）策略，確保符合安全合規要求。
* `網路概念應用`：掌握VPC、防火牆的網路基礎知識，設計和管理安全可靠的雲端網路架構。
* `高效能架構設置`：規劃和設置高可用性和高效能的雲端架構，使用負載均衡(Load balancing)和自動縮放(Auto Scaling)等技術來優化系統效能。
* `業務連續性與災難恢復`：設計並執行業務連續性和災難恢復（BC/DR）計畫，確保資料和服務的持續性和可恢復性。
* `系統監控與故障排除`：使用監控工具監控雲資源和應用程式的效能和可用性，能夠有效排除和解決系統故障。
* `部署和實施雲端解決方案`：協助部署和管理雲端應用，使用自動化工具（如Terraform、Ansible）進行持續部署和配置管理，確保應用的成功執行。

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
