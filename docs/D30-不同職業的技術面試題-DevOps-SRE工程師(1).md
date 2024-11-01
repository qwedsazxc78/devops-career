# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D30-不同職業的技術面試題-DevOps-SRE工程師(1)

## 工商時間

現在跟博碩文化合作寫的書，已經在網路書店販售了！有需要的人可以點擊下面連結！`

[翻轉職涯！雲端 / DevOps / SRE 工程師轉職必殺技：四大步驟帶你找出職能優勢、成功精準轉職的規劃指南（iThome鐵人賽系列書）](https://heyurl.cc/lQ3e4)

![books](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/books.png)

## 章節目標

> 快速了解 `DevOps-SRE工程師` 技術面試問題與核心能力

![D30-不同職業的技術面試題-DevOps-SRE工程師(1)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D31.png)

DevOps-SRE工程師也是市場成長迅速，後市看漲的受歡迎職業，這邊提供技術相關面試的內容，這邊也是吃硬底子！今天的文章專注在 `DevOps-SRE工程師核心能力與基礎知識` 。

作為一名DevOps或SRE工程師，你需要具備 `具備廣泛的雲端技術知識和實踐經驗，以及強大的團隊溝通能力，並且能夠設計和維運高效的系統` ，以下是這個職位要求的核心能力

## DevOps-SRE工程師核心能力

* `雲端服務知識`：熟悉至少一個主要雲端服務平台（如AWS、GCP、Azure）的管理控制台和核心服務（如計算、儲存、網路、資料庫）。除了能夠設置和管理雲端基礎設施，還可以運用更多系統設計概念，確保其高可用性和擴展性。
* `操作系統管理`：熟練操作和管理Linux和Windows作業系統，能夠進行系統安裝、配置、管理和故障排除。能夠在雲端環境中管理和優化虛擬機和容器。
* `持續交付與自動化`：設計和實施持續交付（CI/CD）流水線（pipeline），確保軟體能夠快速且可靠地部署到生產環境。使用自動化工具（如Jenkins、GitLab CI、Terraform、Ansible ）進行配置管理和基礎設施自動化。
* `安全控制與合規`：實施並自動化安全控制、治理流程和合規驗證，管理雲端環境中的身分和訪問管理（IAM）策略，確保符合安全合規要求。定期進行安全審計和風險評估，確保系統和資料的安全性。
* `系統監控與故障排除`：定義和部署監控、指標和日誌系統（如Prometheus、Grafana、ELK Stack ），監控系統效能和可用性。能夠快速識別和解決系統故障，確保服務的穩定執行。
* `高可用性與可擴展性`：設計和實施高可用性、可擴展和自我修復的系統架構，使用負載均衡(Load balancing)和自動縮放(Auto Scaling)技術來優化系統效能。確保系統在高負載情況下的穩定性和響應能力。
* `自動化營運流程`：設計、管理和維護自動化營運流程，確保營運效率和系統穩定性。使用自動化工具和腳本（如Python、Bash）來簡化重複性任務和流程。
* `業務連續性與災難恢復`：設計並執行業務連續性和災難恢復計畫，確保資料和服務的持續性和可恢復性。使用快照、備份和多區域部署等技術來保障業務連續性。
* `網站可靠性工程實踐（SRE）` ：將網站可靠性工程實踐應用於服務，實施服務監控策略，優化服務效能，並確保系統的可靠性和可用性。定期進行效能測試和容量規劃，確保系統能夠應對未來的需求增長。

## Q1.【基礎知識】請簡單說明Kubernetes中Control Plane和Data Plane的差異，請問對應到AWS或是GCP上是哪些服務？

* `主考官的目的`：測試你對容器化服務kubernetes的核心概念以及對應的雲端服務，因為這是此職位的核心能力之一。
* `準備方式`：基礎知識的準備考驗你對工作的理解，建議重點複習`雲端服務中所有的服務內容`，同時需要理解更多底層知識，這是此職位的必要知識。
* `參考標準`： 熟悉現代容器操作平台Kubernetes的使用以及底層原理，Control Plane和Data Plane是Kubernetes架構的兩個主要部分，基本上也是面試問題的起手式。

我們利用這張圖說明了關於Kubernetes 集群中控制平面（Control Plane）和資料平面（Data Plane）的區別！
詳細的Kubernetes內部元件，我們則利用表來做逐項的說明

* 控制平面（Control Plane）: 負責管理和控制集群，維持集群的期望狀態。
* 資料平面（Data Plane）: 負責執行應用和處理資料，實際執行容器化的工作負載。

![Control Plane 和 Data Plane 階層示意圖](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D30-1.png)

### Control Plane和 Data Plane的差異

Control Plane和Data Plane在Kubernetes中各自扮演不同的角色，下表比較兩者的差異。

| 項目 | 說明 |
| ---- | ---- |
| Control Plane (Control Node) | - 功能：負責管理和控制集群，維持集群的期望狀態。 |
|                         |   - 元件：包括 API Server、Scheduler、Controller Manager 和 etcd。 |
|                         |   - API Server：處理所有的 RESTful API 請求，並提供集群的狀態資訊。 |
|                         |   - Scheduler：根據資源需求和策略將新建立的 Pod 分配到適當的 Node 上。 |
|                         |   - Controller Manager：監控集群狀態並確保系統部署 pod 處於所期望的狀態。 |
|                         |   - ETCD：分布式鍵值儲存，用於保存集群的所有資料。 |
| Data Plane (Worker Node pool) | - 功能：負責執行應用和處理資料，實際執行容器化的工作負載。 |
|                         |   - 元件：主要由 Node 上的 kubelet、kube-proxy 和 container runtime（容器執行時）組成。 |
|                         |   - kubelet：執行在每個 Node 上，管理 Pod 的生命周期。 |
|                         |   - kube-proxy：負責網路代理和負載均衡，確保網路正常。 |
|                         |   - container runtime（容器執行時）：如 Docker、Containerd 和 CRI-O，負責拉取和執行容器。 |

在了解Control Plane和Data Plane在Kubernetes的差異後，我們來比較一下AWS或GCP上的雲端服務差異，詳見下表

### AWS 或 GCP 上的 Kubernetes 雲端服務

| 雲端平台 | 雲端服務 | 說明 |
| ---- | ---- | ---- |
| AWS | Control Plane | Amazon EKS (Elastic Kubernetes Service) 會自動管理 Kubernetes 的 Control Plane。 |
|  | Data Plane | 由 Amazon EC2 虛擬機器執行，這些虛擬機器節點作為 Kubernetes 的 Worker Nodes，承載實際的應用程式工作負載。 |
| GCP | Control Plane | Google Kubernetes Engine (GKE) 會自動管理 Kubernetes 的 Control Plane。 |
|  | Data Plane | 由 GKE 中的 Google Compute Engine (GCE) 虛擬機器節點執行，這些虛擬機器節點作為 Kubernetes 的 Worker Nodes，承載實際的應用程式工作負載。 |

## 延伸問題一：請說明Kubernetes中的自動擴展功能（HorizontalPodAutoscaler和Cluster Autoscaler）的運作原理及其應用場景。

`參考回答` ：自動擴展是Kubernetes中非常重要的核心功能，需要對其多多了解，參考下表的詳細解釋！

| 功能 | 說明 |
| ---- | ---- |
| HorizontalPodAutoscaler (HPA) | HPA 根據 CPU/RAM 使用率或其他自定義指標自動調整Pod的預期數量，以應對流量變化。例如：當 CPU 使用率高於設定閾值時，HPA 會自動增加Pod數量以分散負載。 |
| Cluster Autoscaler | Cluster Autoscaler 根據集群中未滿足的Pod需求，自動調整節點 (Nodes) 的數量，確保集群資源的動態擴展。例如：當某些Pod因資源不足無法調度時，Cluster Autoscaler 會自動增加更多的節點。 |

## 延伸問題二：在Kubernetes中，如何使用ConfigMap和Secret來管理應用配置和敏感訊息？請提供一個具體的應用場景。

`參考回答` ：ConfigMap和Secret是Kubernetes中用來儲存配置資料的功能，詳細了解兩者的差異與使用時機非常重要！

| 功能 | 說明 |
| ---- | ---- |
| ConfigMap | ConfigMap 用於儲存非敏感的配置資料，例如：應用的環境變數、設定檔案。這些配置資料可以被注入到Pod中。另外一個例子為：在一個多環境部署的應用中，可以使用ConfigMap來管理不同環境的配置，根據需要動態載入。 |
| Secret | Secret 用於儲存敏感資料，如密鑰、API 密鑰等。這些資料在應用執行時可以安全地注入到Pod中。例如：當應用需要連接到第三方 API 時，可以使用Secret來儲存API密鑰，並在Pod中安全使用。 |

## 本日總結

第30天的文章，我們專注於了解 `不同職業的技術面試題-DevOps-SRE工程師` 的技術面試，文章中先了解 `DevOps-SRE工程師核心能力` ，在立刻來個 `Q1.【基礎知識】請簡單說明Kubernetes 中Control Plane和Data Plane的差異，請問對應到AWS或是GCP上是哪些服務？` ，用來驗證你的雲端與容器化相關基礎知識。從這個問題，可以簡單的驗證你自己是否了解現代容器化操作系統的概念，根據自己的不足再調整應該進修的方向。

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
