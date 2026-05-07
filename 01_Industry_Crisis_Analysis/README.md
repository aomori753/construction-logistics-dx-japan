# Module 01: Industry Crisis Analysis / 業界の危機分析
## Defining the "Problem Space" for Systems Architecture / システムアーキテクチャのための「問題領域」の定義

**Repository:** [construction-logistics-dx-japan](https://github.com/aomori753/construction-logistics-dx-japan)
**Module Status:** Active — Living Document | **言語:** English and Japanese (最高敬語)

---

> *"You cannot architect a solution to a problem you have not yet precisely defined. This module is the precise definition."*
>
> *「問題を精確に定義することなく、解決策を設計することはできません。本モジュールは、その精確な定義そのものでございます。」*

---

## ⚠️ Research & Policy Compliance Disclaimer / 研究およびコンプライアンスに関する免責事項

> This module is an independent research and self-development framework authored by Jericho Ong, a construction operations professional actively transitioning into information technology in Japan. All analysis draws exclusively from publicly available government publications, industry association reports, academic sources, and 13 years of direct operational field experience in the Philippine construction sector. This module does not represent any government body, institution, or employer in the Philippines or Japan. It does not constitute legal, regulatory, engineering, or professional advice under the laws of either nation. All referenced statistics and policy details are drawn from primary public sources and are intended for educational and portfolio purposes only.
>
> 本モジュールは、日本においてIT分野へのキャリア転換を積極的に進めている建設業オペレーション専門家、翁ジェリコが独自に作成した研究・自己研鑽フレームワークでございます。すべての分析は、政府刊行物・業界団体報告書・学術資料といった公開情報、およびフィリピン建設業界における13年間の直接的な現場経験に基づくものです。本モジュールは、フィリピンおよび日本のいかなる政府機関・機構・雇用主をも代表するものではなく、両国の法律のもとにおける法的・規制的・工学的・専門的助言を構成するものでもございません。

---

## 1. Mission Alignment / リサーチミッションとの整合性

The mission of this repository is to bridge the gap between **Physical Operations (Ground Truth)** and **Digital Architecture**. Module 01 functions as the "Requirements Discovery" phase of this systems engineering framework. In professional systems architecture, no solution can be responsibly designed without first quantifying the structural failures, legislative constraints, and demographic pressures of the current operational environment.

Every technical proposal in Modules 02 through 09 of this repository is grounded in the problem space established here. The IoT sensor networks, Digital Twin architectures, JIT material delivery API concepts, and Physical AI protocols addressed in later modules are not theoretical exercises — they are direct engineering responses to the specific, measurable crises documented in this module.

本リポジトリのミッションは、**実務運用（現場の真実）**と**デジタルアーキテクチャ**の懸け橋となることです。第01章は、このシステムズエンジニアリングフレームワークの「要件定義」フェーズとして機能します。プロフェッショナルなシステムアーキテクチャにおいては、現在の業務環境における構造的欠陥・法的制約・人口動態的圧力を定量化することなしに、解決策を責任をもって設計することはできません。

本リポジトリのモジュール02から09に示されるすべての技術的提案は、ここで確立される問題領域に根拠を置いております。後続モジュールで取り上げるIoTセンサーネットワーク・デジタルツインアーキテクチャ・JIT資材搬入API構想・フィジカルAIプロトコルは理論的演習ではなく、本モジュールで記録される特定かつ定量可能な危機への直接的なエンジニアリング対応でございます。

---

## 2. Theoretical Framework / 理論的枠組み

This module applies **Top-Down Systems Decomposition** to analyze the 2024 Problem not merely as a labor shortage, but as a **Throughput Crisis** — a systemic failure in which the capacity of human operators to coordinate physical work has been legally constrained below the minimum threshold required to fulfill existing contractual and national infrastructure obligations.

The construction site is analyzed as a **volatile node within a constrained network** — receiving inputs from a logistics supply chain that is simultaneously operating under its own independent set of regulatory constraints. The intersection of these two constrained systems at a single physical location produces a compounding failure mode that neither sector can resolve independently.

### Key Analytical Pillars / 主要分析軸

**Capacity Constraints:** The 45-hour monthly overtime cap and the 960-hour annual driver limit function as hard system boundaries — non-negotiable parameters within which all operational planning must occur. This transforms what was previously a scheduling problem into a systems architecture problem.

**Demographic Fragility:** The erosion of Japan's supervisory labor pool — with 36 percent of construction workers aged 55 and above — represents not merely a headcount shortage but a failure of knowledge transfer. The institutional expertise embedded in the 施工管理 certification system is aging out faster than it can be replaced or digitized.

**Infrastructure Interoperability:** The absence of API-level communication between logistics fleets, material suppliers, and construction site gate management systems means that every delivery coordination event relies on informal human communication — a system architecture that is inherently unscalable and incompatible with the regulatory constraints introduced in April 2024.

本モジュールは、**トップダウン型システム分解**を適用し、2024年問題を単なる労働力不足としてではなく、**スループット危機**として分析します。すなわち、物理的作業を調整する人的オペレーターの能力が、既存の契約的・国家インフラ的義務を履行するために必要な最低限のしきい値を下回るよう法的に制約されるというシステム的障害として捉えるものでございます。

---

## 3. Module Roadmap & File Taxonomy / モジュール構成と文書分類

The four documents in this module are designed to be read in sequence. Each document builds upon the analytical foundation established by the previous one, leading from legislative origin through sectoral impact to systemic intersection and policy mandate.

| Document / 文書 | Systems Engineering Focus / システム工学的焦点 | Standard |
|:---|:---|:---|
| **[2024-problem-overview.md](./2024-problem-overview.md)** | **Throughput Analysis:** How legislative overtime caps break the informal buffer systems upon which both construction and logistics have historically depended. | PhD Level |
| **[construction-labor-impact.md](./construction-labor-impact.md)** | **Resource Constraint Modeling:** Quantifying the collapse of the supervisory ratio and the permanent loss of Takumi-level knowledge under demographic and regulatory pressure. | PhD Level |
| **[logistics-supply-chain-bottlenecks.md](./logistics-supply-chain-bottlenecks.md)** | **Endpoint Volatility Analysis:** Modeling the construction site gate as a dynamic, unmanaged logistics endpoint and examining the compounding failure when two constrained systems intersect. | PhD Level |
| **[japan-dx-policy-landscape.md](./japan-dx-policy-landscape.md)** | **Compliance Architecture:** Mapping MLIT i-Construction mandates, IPA security standards, and national DX policy frameworks to technical system requirements. | PhD Level |

---

## 4. Relationship to National Standards / 国家基準との整合性

The research contained in this module is explicitly aligned with the following national policy frameworks and institutional standards:

**MLIT (国土交通省 / Ministry of Land, Infrastructure, Transport and Tourism):** The i-Construction 2.0 initiative and the BIM/CIM mandate for all public works projects. The labor and logistics crises documented here are the direct operational drivers that make MLIT's digital mandates economically and legally necessary rather than merely aspirational.

**IPA (独立行政法人情報処理推進機構 / Information-technology Promotion Agency, Japan):** The security and reliability frameworks governing digital infrastructure in Japan's social infrastructure sectors. The systems architecture proposals in subsequent modules are designed for alignment with IPA standards at the FE, AP, and SC examination levels.

**Logistics DX Policy (物流DX / 物流革新に向けた政策パッケージ):** The national logistics innovation policy framework targeting the elimination of uncompensated waiting times, the digitization of freight booking and gate scheduling, and the modal shift strategy for reducing road freight dependency.

**GX (Green Transformation / グリーントランスフォーメーション):** The intersection of digital transformation with Japan's carbon neutrality commitments, particularly as they apply to construction materials supply chains, site energy management, and equipment emissions monitoring.

本モジュールに収録された研究は、上記の国家政策フレームワークおよび機関標準と明示的に整合しております。国土交通省のi-Construction 2.0とBIM/CIM義務化、情報処理推進機構（IPA）のセキュリティ・信頼性フレームワーク、物流革新に向けた政策パッケージ、およびグリーントランスフォーメーション（GX）との交差点がその主要な整合軸でございます。

---

## 5. Module Connections / モジュール間の接続

This module does not stand in isolation. Its findings directly justify and inform the architectural proposals in all subsequent modules of this repository.

The supervisory bottleneck and knowledge loss documented in Document 2 are the operational drivers for the IoT sensor networks, real-time personnel monitoring systems, and Digital Twin site management concepts addressed in **Module 03: System Architecture Concepts**.

The logistics endpoint volatility and JIT delivery fragility documented in Document 3 are the operational drivers for the material flow frameworks, last-mile delivery analysis, and heavy equipment mobilization models in **Module 04: Construction Logistics Intersection**.

The policy mandates and IPA compliance requirements documented in Document 4 are the regulatory foundation for the security framework alignment and compliance architecture in **Module 06: Policy and Compliance**.

This interconnection is deliberate. The repository functions as a unified systems engineering argument — not a collection of independent documents. Each module is a layer in a single coherent framework.

本モジュールは独立して存在するものではございません。その知見は本リポジトリのすべての後続モジュールにおけるアーキテクチャ的提案を直接的に正当化し、根拠づけます。文書2の監理能力ボトルネックはモジュール03の推進要因、文書3の物流脆弱性はモジュール04の推進要因、文書4の政策義務はモジュール06の法令遵守的基盤となっております。

---

## 5. Strategic Conclusion / 戦略的結論

The objective of this module is to move from **Observation** to **Specification**. Each document contributes to a master list of system requirements that the subsequent architecture modules must address. When a recruiter, a hiring manager, or a technology partner reads this module, they are not reading a summary of news articles. They are reading the requirements definition phase of a serious systems engineering project — authored by a practitioner who has operated inside the problem space being described.

本モジュールの目的は、**観察**から**仕様定義**へと移行することでございます。各文書は、後続のアーキテクチャモジュールが対処しなければならないシステム要件のマスターリストに貢献します。採用担当者・採用責任者・テクノロジーパートナーが本モジュールを読む際、彼らがお読みになるのはニュース記事の要約ではございません。記述されている問題領域の内側で業務を行ってきた実務家によって執筆された、本格的なシステムズエンジニアリングプロジェクトの要件定義フェーズをお読みいただいております。

---

**Author / 執筆者:** Jericho Ong
Jericho Ong | Construction & Logistics DX Independent Researcher (Japan) | 13-Year Construction PM | Python, Data, Cybersecurity | IPA × MLIT × JILS | Exploring Physical AI, Automation, Data Analytics & Embodied Intelligence
*GitHub: [aomori753](https://github.com/aomori753) | Philippines × Japan 🇵🇭🇯🇵*

---

*This module is part of the living knowledge framework at [construction-logistics-dx-japan](https://github.com/aomori753/construction-logistics-dx-japan). Updated as industry conditions, policy mandates, and research findings evolve.*

*本モジュールは [construction-logistics-dx-japan](https://github.com/aomori753/construction-logistics-dx-japan) の継続的な知識フレームワークの一部です。産業動向・政策指針・研究知見の変化に応じて随時更新されます。*
