# PART 4 面試技巧：展現最好的自己

![鐵人賽-30Days-P4](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/30Days-P4.png)

## D29-不同職業的技術面試題-System Admin系統管理員-MIS資訊系統工程師(2)

## 章節目標

> 快速了解 `System Admin系統管理員-MIS資訊系統工程師` 技術面試問題與核心能力

![D29-不同職業的技術面試題-System Admin系統管理員-MIS資訊系統工程師(2)](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D29.png)

今天的文章專注在System Admin系統管理員-MIS資訊系統工程師的第二個問題，來到比較難的 `系統設計` ！

## Q2.【系統設計】如何設計地端機房以及雲端機房的網路連線？並且做好安全防護？

* `主考官的目的`：測試你對企業網路配置與系統連結的理解，並提供對應的解決方案，這是一道較具挑戰性的考題。
* `準備方式`：系統設計考題較難準備，建議整理過往工作經驗中複雜系統的實例，列出當時如何執行的方式作為參考。
* `參考標準`：設計地端機房和雲端機房的網路連線，最常見的方法是使用`site-to-siteVPN`來建立安全連線。回答到 `S2S VPN`，即可顯示你對雲端與地端網路連線的理解，如果能進一步提及防火牆等安全防護措施，會使回答更全面。

下表是更詳細的常見可行方案，一般來說，不需要記得這麼詳細，關鍵是知道在哪裡找到相關資源來解決問題，詳細資料可以參考下面三個連結

* [GCP HAVPNtopologies 設計參考](https://cloud.google.com/networkconnectivity/docs/vpn/concepts/topologies)
* [GCP 核心架構基礎知識](https://www.cloudskillsboost.google/course_templates/60)
* [AWS站對站VPN設置](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html）)

### 設計地端機房和雲端機房的詳細方案

| 項目 | 方案 |
| ---- | ---- |
| 網路連線設計 | - 專線連接：使用虛擬私人網路 (VPN) 或專用雲地端連接 (interconnect)，確保地端機房與雲端機房之間的資料傳輸穩定且快速。 <br> - 冗餘網路：設計冗餘網路，避免單點故障，確保網路高可用性，如設定 HAVPN連線。 |
| 安全防護 | - 防火牆：設置邊界與地端防火牆，控制進出流量，防止未經授權的訪問。 <br> - 入侵檢測與防禦系統 (IDS/IPS)：監控並防禦網路攻擊，保護系統安全。通常會設在地端防火牆上，如 Fortinet 的防火牆，雲端則看各家公司有雲方案。 <br> - 資料加密：對傳輸資料進行加密，確保資料機密性與完整性，避免使用未加密通道，務必使用 TLS 1.2 以上的加密。 <br> - 身分驗證與訪問控制：實施 IAM 身分驗證機制，確保僅授權使用者可訪問系統資源，並針對不同用戶群組設定不同權限。 |

### HA VPN與地端連線示意圖 (一般不會考這麼難，但可以增強自己技能)

這張架構圖展示了在Google Cloud上設定高可用性（HA）VPN 的架構圖，說明如何將內部的本地端網路（On-premises network）透過高可用性的VPN網關連接到Google Cloud的虛擬私有雲（VPC），確保連線的穩定性與安全性。

`架構說明` ：

1. `高可用性VPN連線`：此架構透過兩個VPN隧道(VPN tunnel)來實現高可用性，這確保即使其中一個VPN隧道失效，另一個隧道仍可保持連接，從而提供冗餘。
2. `雙向動態路由`：使用BGP（Border Gateway Protocol）進行路由交換，以便本地端與Google Cloud 之間動態更新路由資訊，讓兩邊的子網（Subnet）可以相互通信。
3. `跨區域網路`：顯示在不同的GCP區域（us-west1 和 us-central1）中設有子網，表示這個架構支持多區域的部署，並且各區域的資源都可以透過VPN進行連接。
4. `安全加密通道`：VPN隧道(VPN tunnel)密了通過互聯網傳輸的流量，確保本地端網路與 Google Cloud 之間的數據安全。
5. `Cloud Router`：動態管理和交換路由資訊，分配流量在子網與VPC之間的溝通。

這是典型的混合雲設計，用來將本地端基礎設施與雲端無縫連接。

![HA VPN與地端連線示意圖](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D29-1.png)

資料來源：https://cloud.google.com/network-connectivity/docs/vpn/concepts/topologies

### GCP與地端網路連接方式 (一般不會考這麼難，但可以增強自己技能)

這是進階的架構設計，幫助挑選對應的雲端基礎設施連接，架構圖展示在Google Cloud中如何選擇適當的網路連接方式，依據使用場景與需求來判斷使用 Direct Peering、Carrier Peering、Cloud VPN、Partner Interconnect 或 Dedicated Interconnect 等解決方案。幫助企業根據自身的需求選擇合適的Google Cloud網路連接方案，無論是透過公網加密（VPN）還是專線（Interconnect）來確保高效、安全的雲端基礎設施連接。

`架構說明` ：

1. `雲端基礎設施連接`：主要流程是引導使用者如何將自己的基礎設施連接到 Google Cloud。這包括是否需要直接連接 Google Workspace/YouTube 或是更廣泛地擴展至Google Cloud的網路。
2. `不同的連接方式`：
   - `Direct Peering & Carrier Peering` ：適合需要連接到 Google 服務（如 Workspace 或 YouTube）的使用者，但要滿足 Google 的 Peering 要求。
   - `Partner Interconnect & Dedicated Interconnect` ：如果需要更高帶寬或多雲連接，或者使用者希望在某個 Google 的共置設施中進行對接，這兩種選項會提供高效的連接能力，Partner Interconnect 更適合10 Gbps以下的連線需求。
   - `Cloud VPN` ：適用於短期、較低帶寬需求，並且希望通過加密通道來保護流量的場景。
3. `安全性與敏感流量加密`：圖中的一部分探討了對於敏感流量，是否需要自行設計加密機制，如果是，則需要進一步考慮更高級的連接選項。

![GCP與地端網路連接方式](https://github.com/qwedsazxc78/devops-career/raw/main/docs/img/D29-2.png)

資料來源：https://www.cloudskillsboost.google/course_templates/60

## 本日總結

第29天的文章，我們專注於了解 `Q2.【系統設計】如何設計地端機房以及雲端機房的網路連線？並且做好安全防護？` ，系統設計題目今天的真的是非常硬喔，網路架構不是可以輕鬆寫意的回答出來的，需要深厚的功力。系統設計問題，可以知道你是否了解現代流行的雲端基礎設施連接，會針對網路的部分，更進一步還可能會問到地端的防火牆(Firewall)或L3管理型交換機(L3 Managed Switch)，真的都是非常進階的學問。

* 如果文章的技術面試都能夠回答得非常好，恭喜你！你的功力非常深厚，可以持續邁進！
* 如果文章的技術面試沒有太過理解，沒事的，現在開始努力都來得及！繼續看下去提升你的實力！

System Admin系統管理員-MIS資訊系統工程師的技術面試，會相對針對在資訊系統與網路基礎設施的認識與使用，如同前面說明的核心能力。最後再藉由工作經驗的提升，逐漸在往DevOps/SRE等進階工種邁進，但也是需要更多的知識積累。

* `熟悉操作系統`：能夠操作和管理Linux、Windows、macOS的作業系統。
* `雲端服務知識`：使用過至少一個雲端服務（如AWS、GCP、Azure）的管理控制台，對大部分的服務有基本的認識。
* `權限與安全控制`：針對企業中的資訊系統，能夠實施權限與安全控制以滿足合規要求。
* `系統監控與故障排除`：監控、記錄和排除系統故障，範圍涵蓋雲端與地端伺服器。
* `網路概念應用`：掌握DNS、TCP/IP、防火牆等網路概念，管理企業內部的網路架構。
* `高效能架構設置`：協助設置高可用性、效能和容量要求的高效能架構。
* `業務連續性與災難恢復`：執行業務連續性和災難恢復程序，確保資料和服務的持續性和可恢復性，以及定期的軟體更新。
* `資訊事件管理`：識別、分類和修復突發資訊事件，以及防護可能的資訊安全問題。

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
