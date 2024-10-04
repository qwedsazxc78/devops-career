# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D26-不同職業的技術面試題-Cloud Engineer雲端工程師(1)

## 章節目標

> 快速了解 `Cloud Engineer雲端工程師` 技術面試問題與核心能力

![D26-不同職業的技術面試題-Cloud Engineer雲端工程師(1)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D26.png)

終於寫到了技術相關面試的文章，這邊吃的就是硬底子了！今天的文章專注在 `Cloud Engineer雲端工程核心能力與基礎知識` 。

作為一名Cloud Engineer，你需要具備 `雲端技術的基礎知識和實踐經驗` ，以下是這個職位要求的核心能力

## Cloud Engineer雲端工程師核心能力

* `雲端服務知識`：熟悉至少一個主要雲端服務平台（如AWS、GCP、Azure）的管理控制台和核心服務（如計算、儲存、網路、資料庫）。
* `操作系統管理`：能夠操作和管理Linux、Windows等作業系統，進行雲端虛擬系統的安裝、配置、管理和故障排除。
* `權限與安全控制`：實施並管理雲端環境中的身分和訪問管理（IAM）策略，確保符合安全合規要求。
* `網路概念應用`：掌握VPC、防火牆的網路基礎知識，設計和管理安全可靠的雲端網路架構。
* `高效能架構設置`：規劃和設置高可用性和高效能的雲端架構，使用負載均衡(Load balancing)和自動縮放(Auto Scaling)等技術來優化系統效能。
* `業務連續性與災難恢復`：設計並執行業務連續性和災難恢復（BC/DR）計畫，確保資料和服務的持續性和可恢復性。
* `系統監控與故障排除`：使用監控工具監控雲資源和應用程式的效能和可用性，能夠有效排除和解決系統故障。
* `部署和實施雲端解決方案`：協助部署和管理雲端應用，使用自動化工具（如Terraform、Ansible）進行持續部署和配置管理，確保應用的成功執行。

## Q1.【基礎知識】請問Docker Container與Virtual Machine的差異，請問AWS或GCP上是哪些服務?

* `主考官的目的`：測試你對容器化服務的核心概念及對應的雲端服務，因為這是此職位的核心能力之一。
* `準備方式`：基礎知識的準備考驗你對`工作的理解`，建議重點複習雲端服務裡面所有的服務內容，這是此職位的必要知識。
* `參考標準`：Docker Container容器和VM虛擬機器都是用來`隔離應用程式執行環境的技術`，但它們有著不同的運作方式和優缺點，參見Docker容器和VM虛擬機器比較表與Docker容器和VM虛擬機器架構圖來深入了解兩者的差異。後續在了解`AWS或GCP上的雲端服務`，對應到哪些Docker容器和VM虛擬機器服務。

Docker容器和VM虛擬機器架構圖

![Docker容器和VM虛擬機器架構圖](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D26-1.png)

### Docker容器和VM虛擬機器比較表

這邊會分成四個方向來說明Docker容器和VM虛擬機器的比較，確定自己有理解下表中的內容，再搭配Docker容器和VM虛擬機器架構圖服用，效果更佳！

| 項目 | VM 虛擬機器 | Docker 容器 |
| ---- | ---- | ---- |
| 架構 | 基於虛擬化技術，每個虛擬機器包含完整的操作系統和應用程式，執行在虛擬化層之上。 | 基於容器技術，使用共享的操作系統內核，每個容器執行在其自己的隔離用戶空間中。 |
| 效能 | 啟動速度慢，資源開銷大，因為每個虛擬機器需要獨立的操作系統。 | 啟動速度快，資源開銷低，因為容器共享宿主 (Host) 操作系統的內核。 |
| 靈活性 | 適合需要完整隔離和多操作系統的場景。 | 更靈活，適合微服務架構和持續交付。 |
| 例子 | 需要使用軟體整個的程序，使用單體應用架構 (Monolithic)。 | 應用程式無需狀態化，在高流量系統中，方便自動擴展 (auto scaling)。 |

### AWS或GCP上的雲端服務

這邊介紹Docker容器和VM虛擬機器對應到雲端的服務，可以看到下表有AWS或GCP上的雲端服務。主要分類有三個，分別是虛擬機器、Docker容器與Kubernetes的託管服務。

| 雲端平台 | 雲端服務 | 說明 |
| ---- | ---- | ---- |
| AWS | Amazon EC2 (Elastic Compute Power) | 提供可調整的虛擬機器服務。 |
|  | Amazon ECS (Elastic Container Service) | 高可擴展的 Docker 容器管理服務。 |
|  | Amazon EKS (Elastic Kubernetes Service) | 用於執行 Kubernetes 的託管服務。 |
| GCP | Google Compute Engine (GCE) | 提供可調整的虛擬機器服務。 |
|  | Google Cloud Run | 管理和執行無伺服器容器的完全託管服務。 |
|  | Google Kubernetes Engine (GKE) | 用於執行 Kubernetes 的託管服務。 |

## 本日總結

第26天的文章，我們專注於了解 `不同職業的技術面試題-Cloud Engineer雲端工程師` 的技術面試，文章中先了解 `Cloud Engineer雲端工程師核心能力` ，在立刻來個牛刀小試，驗證你的雲端基礎知識。從 `Q1:【基礎知識】請問Docker Container與Virtual Machine的差異，請問AWS或GCP上是哪些服務?` 這個問題，可以簡單的知道你是否了解現代流行的容器解決方案，從基礎知識到雲端代表服務。

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
