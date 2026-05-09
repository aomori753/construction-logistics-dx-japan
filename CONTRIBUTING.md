# Contribution Guidelines and Methodological Framework
## コントリビューション・ガイドラインおよび方法論的枠組み

**Repository:** `construction-logistics-dx-japan`
**Maintainer:** Jericho Ong | Construction & Logistics DX Independent Researcher
**Target Standards:** MLIT i-Construction, IPA Systems Architecture, JILS Logistics DX

---

## 1. Introduction and Governance / はじめにおよびガバナンス

The `construction-logistics-dx-japan` repository operates as an applied systems engineering knowledge framework. Its primary objective is to mathematically and architecturally resolve the integration gap between construction site operations ("Ground Truth") and macro-level logistics technology. 

This document outlines the mandatory protocols for submitting architectural blueprints, policy analyses, or empirical data to this framework. All contributions must demonstrate empirical validity, structural logic, and strict alignment with the regulatory mandates currently driving Japan's industrial sector.

> 本リポジトリ（`construction-logistics-dx-japan`）は、応用システムズエンジニアリングの知識フレームワークとして運用されております。その主要な目的は、建設現場のオペレーション（「現場の真実」）とマクロレベルの物流テクノロジーとの間の統合的なギャップを、数理的かつアーキテクチャ的に解決することにあります。
> 
> 本書は、本フレームワークに対するアーキテクチャ設計図、政策分析、または実証データの提出に関する必須プロトコルを概説するものです。すべての貢献は、実証的妥当性、構造的論理、および現在の日本の産業セクターを牽引する規制要件との厳格な整合性を実証しなければなりません。

---

## 2. Scope of Acceptable Contributions / 受け入れ可能な貢献の範囲

We accept pull requests (PRs) that fall strictly within the following methodological paradigms:

### Category A: Policy and Regulatory Harmonization
Analysis of new legal frameworks, subsidy programs, or digital mandates.
* **Requirement:** Must include direct citations to primary government publications (e.g., MLIT White Papers, Ministry of Health, Labour and Welfare labor data).

### Category B: Systems Architecture and API Specifications
Technical blueprints detailing integration protocols.
* **Requirement:** Proposed IoT network topologies, Digital Twin synchronization models, or JIT (Just-In-Time) API data structures must align with IPA (Information-technology Promotion Agency) security and reliability frameworks.

### Category C: Empirical Operational Data and Modeling
Data models quantifying throughput bottlenecks or labor deficits.
* **Requirement:** Must utilize verified statistical modeling. Speculative data without methodological transparency will be rejected.

> 以下の方法論的パラダイムに厳密に合致するプルリクエスト（PR）のみを受け入れます：
> 
> ### カテゴリーA：政策および規制の整合性
> 新たな法的枠組み、補助金制度、またはデジタル指令の分析。
> * **要件:** 第一次政府刊行物（例：国土交通省白書、厚生労働省データ）への直接的な引用が必須となります。
> 
> ### カテゴリーB：システムアーキテクチャおよびAPI仕様
> 統合プロトコルを詳述する技術的設計図。
> * **要件:** 提案されるIoTネットワーク構成、デジタルツイン同期モデル、またはJIT APIデータ構造は、IPAのセキュリティおよび信頼性フレームワークに準拠している必要があります。
> 
> ### カテゴリーC：実証的な運用データとモデリング
> スループットのボトルネックや労働力不足を定量化するデータモデル。
> * **要件:** 検証済みの統計的モデリングを使用する必要があります。透明性を欠く推測的なデータは却下されます。

---

## 3. Local Setup and Git Flow / ローカル環境構築およびGitフロー

Contributors must follow a standard enterprise Git flow to ensure repository stability.

### 3.1 Repository Initialization
1. Fork the repository to your local GitHub account.
2. Clone the forked repository to your local machine:
   `git clone https://github.com/YOUR-USERNAME/construction-logistics-dx-japan.git`
3. Add the upstream repository to synchronize ongoing changes:
   `git remote add upstream https://github.com/aomori753/construction-logistics-dx-japan.git`

### 3.2 Branch Nomenclature
Never commit directly to the `main` branch. Create a feature branch utilizing the following structural prefixes:
* `arch/` : For system architecture, API specs, or technical diagrams.
* `policy/` : For updates related to MLIT, JILS, or Japanese legal frameworks.
* `model/` : For statistical data, mathematical routing models, or labor analytics.
* `docs/` : For linguistic corrections, literature additions, or general formatting.

Example: `git checkout -b arch/iot-sensor-topology-update`

> 貢献者は、リポジトリの安定性を確保するため、標準的なエンタープライズGitフローに従う必要があります。
> 
> ### 3.1 リポジトリの初期化
> 1. 本リポジトリを自身のGitHubアカウントにフォークしてください。
> 2. フォークしたリポジトリをローカルマシンにクローンしてください。
> 3. 継続的な変更を同期するため、アップストリーム・リポジトリを追加してください。
> 
> ### 3.2 ブランチ命名規則
> `main`ブランチへの直接のコミットは固く禁じます。以下のプレフィックスを使用したフィーチャーブランチを作成してください：
> * `arch/` : システムアーキテクチャ、API仕様、または技術図解。
> * `policy/` : 国土交通省、JILS、または日本の法制度に関する更新。
> * `model/` : 統計データ、数理ルーティングモデル、または労働分析。
> * `docs/` : 言語的修正、文献の追加、または一般的なフォーマット調整。

---

## 4. Architectural and Syntactic Standards / アーキテクチャおよび構文の基準

To preserve the academic rigor of this framework, all pull requests must clear the following formatting thresholds:

1. **Bilingual Professionalism:** All core documentation must be presented in academic-grade English and formal business Japanese (Keigo / 最高敬語). 
2. **Tone Restriction:** The use of colloquialisms, informal abbreviations, emotional language, and markdown emojis is strictly prohibited.
3. **Citation Standards:** External data must be cited using standard academic referencing structures. Include the author/issuing body, document title, URL, and publication year.

> 本フレームワークの学術的厳密性を維持するため、すべての提出物は以下のフォーマット基準をクリアしなければなりません：
> 
> 1. **二言語の専門性:** すべての中核的ドキュメントは、学術レベルの英語および正式なビジネス日本語（最高敬語）で記述されなければなりません。
> 2. **文体の制限:** 口語表現、非公式な略語、感情的な表現、およびマークダウンの絵文字の使用は固く禁じられております。
> 3. **引用基準:** 外部データは標準的な学術引用形式を用いて明記する必要があります。著者/発行機関、文書名、URL、および発行年を含めてください。

---

## 5. The Pull Request (PR) Lifecycle / プルリクエスト（PR）のライフサイクル

Submissions undergo a rigorous architectural review mirroring enterprise integration processes.

### Step 1: Epistemological Proposal (Issue Creation)
Before drafting extensive documentation, open an "Issue" defining the problem statement, the proposed architectural solution, and the empirical justification.

### Step 2: Commit Metadata Requirements
Commit messages must define the rationale and technical impact of the change.
* Format: `[Prefix]: [Short Summary]`
* Example: `arch: define API payload structure for JIT concrete delivery`

### Step 3: PR Submission
Push your branch to your fork and open a Pull Request against the `main` branch of the upstream repository. The PR description must explicitly declare compliance with MLIT/IPA standards and confirm that no proprietary corporate data has been exposed.

### Step 4: Architectural Validation
The maintainer will review the submission against ground-truth operability and systemic logic. Revisions may be requested to ensure alignment with the overarching ontology.

> 提出物は、企業のシステム統合プロセスを反映した厳格なアーキテクチャ審査を受けます。
> 
> ### ステップ1：認識論的提案（Issueの作成）
> 大規模な文書を作成する前に、「Issue」を作成し、問題定義、提案する解決策、および実証的根拠を明確にしてください。
> 
> ### ステップ2：コミットメタデータの要件
> コミットメッセージには、変更の根拠と技術的影響を定義する必要があります。
> * フォーマット: `[プレフィックス]: [短い要約]`
> 
> ### ステップ3：PRの提出
> ブランチをフォークにプッシュし、アップストリームの`main`ブランチに対してプルリクエストを開いてください。PRの説明には、MLIT/IPA基準への準拠、および企業の機密データが含まれていないことを明記する必要があります。
> 
> ### ステップ4：アーキテクチャの検証
> 管理者は、現場での運用可能性およびシステム的論理に照らして提出物を審査いたします。全体的な概念体系との整合性を確保するため、修正を要請する場合がございます。

---

## 6. Data Integrity and Legal Compliance / データ整合性および法令遵守

Contributors must strictly adhere to corporate Non-Disclosure Agreements (NDAs) and Japanese data privacy laws (Act on the Protection of Personal Information). Do not submit proprietary, sensitive, or classified data, including specific operational blueprints, belonging to current or former employers. All structural models must be generalized or based on publicly available datasets.

> 貢献者は、企業の機密保持契約（NDA）および日本の個人情報保護法を厳格に遵守しなければなりません。現在または過去の雇用主に属する独自のデータ、機密情報、または特定の運用設計図を含む非公開データを提出しないでください。すべての構造モデルは、一般化されているか、または公開されているデータセットに基づいている必要があります。
