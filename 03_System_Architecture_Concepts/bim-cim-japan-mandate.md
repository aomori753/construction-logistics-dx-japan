<div align="center">
  <h1>BIM/CIM Japan Mandate & Semantic Spatial Integration</h1>
  <h3>BIM/CIM原則化と意味論的空間統合：MLIT基準の動的拡張</h3>
</div>

<br>

> **Metadata:**
> * **Document ID:** `MOD-03-02-BIM-CIM-MANDATE`
> * **Project:** Tata Architecture
> * **Status:** 🏗️ Active Specification / 仕様確定
> * **Author:** Jericho T. Ong / ジェリコ・タホネラ・オン (Construction & Logistics DX Independent Researcher)
> * **Language:** English / Japanese (Advanced Technical Business / ビジネス技術日本語)

---

## Executive Summary / 概要

In response to the Ministry of Land, Infrastructure, Transport and Tourism (MLIT) mandating BIM/CIM (Building/Construction Information Modeling) for public works, the domestic construction sector has predominantly treated 3D modeling as a static compliance checkbox—a visual artifact required for procurement rather than an operational engine capable of driving execution. This document fundamentally recontextualizes the MLIT mandate. Within the Tata Architecture, BIM is decisively stripped of its passive, human-centric rendering functions and re-engineered as a **Semantic Spatiotemporal Blueprint**. 

To prepare for the deployment of Physical AI and automated heavy civil engineering, the digital twin cannot be a mere 3D CAD file that requires manual human interpretation. It must function as an immutable, queryable spatial index. This specification outlines the architectural and topological methodology required to transpile static `.ifc` (Industry Foundation Classes) and `.rvt` models into a high-frequency PostGIS environment. By extracting pure geometric bounding boxes and binding them seamlessly to the Event-Sourced Cyber-Physical State Machine detailed in `MOD-03-01`, we transform the static MLIT compliance model into the deterministic neurological grid required to govern autonomous site logistics, robotic routing, and high-throughput material supply chains.

> 国土交通省（MLIT）による公共工事のBIM/CIM原則化に対し、国内の建設業界は概して、3Dモデリングを単なる「コンプライアンス要件の消化」——すなわち、施工を駆動する運用エンジンとしてではなく、調達に必要な静的な視覚的成果物として扱ってまいりました。本文書は、このMLITの要請を根本から再定義するものでございます。Tataアーキテクチャにおきましては、BIMから人間に依存した受動的なレンダリング機能を断固として排除し、自律型現場物流や物理AI（Physical AI）を制御するために不可欠な決定論的空間グリッド、すなわち**「意味論的時空間ブループリント（Semantic Spatiotemporal Blueprint）」**として再構築いたします。
> 
> 物理AIおよび自動化された重土木工学の導入を見据えるならば、デジタルツインは人間の手動による解釈を必要とする単なる3D CADファイルであってはなりません。それは不変かつクエリ可能な「空間インデックス」として機能する必要があります。本仕様書では、静的な`.ifc`（Industry Foundation Classes）や`.rvt`モデルを、高頻度のPostGIS環境へと変換（トランスパイル）するために必要なアーキテクチャおよびトポロジーの手法を規定いたします。純粋な幾何学的バウンディングボックスを抽出し、`MOD-03-01`で詳述いたしましたイベントソース型サイバーフィジカル・ステートマシンとシームレスに結合することで、我々は静的なMLIT準拠モデルを、自律的な現場物流、ロボットのルーティング、および高スループットな資材サプライチェーンを制御するための「決定論的な神経網（Neurological Grid）」へと変貌させるのでございます。

---

## 1. The Limitations of Conventional MLIT Compliance / 従来のMLIT準拠の限界

The fundamental architectural vulnerability of current MLIT BIM/CIM guidelines lies in their exclusive, narrow emphasis on spatial geometry and asset attributes through progressive Levels of Development (LOD). While an LOD 300 or 400 model provides millimeter precision in three-dimensional physical space ($x, y, z$), it possesses absolutely zero resolution in the temporal dimension ($t$). This creates a critical system failure known as **Temporal Data Decay**.

When a site manager manually updates a conventional BIM file or daily schedule at 17:00, that data begins to decay immediately. By 08:00 the following morning, the physical ground truth of the *Genba* has already diverged from the digital twin due to stochastic variables (e.g., sudden weather shifts, micro-delays in concrete curing, unexpected supply chain latency). Consequently, highly detailed geometric models completely fail the test of the "2024 Logistics Problem." 

From a strict queueing theory perspective, if an inbound logistics vector (such as a 10-ton concrete agitator truck) automatically queries a conventional BIM model for the availability of an unloading staging zone, the database returns a stale state variable (e.g., assuming the zone is clear based on yesterday's input). When the truck arrives and finds the physical space occupied by an idle crane, a thread-blocking queue is instantly generated. This forces the physical logistics asset into an unoptimized wait state, burning diesel fuel, destroying strict SLA delivery windows, and cascading latency down the entire supply chain. 

Therefore, conventional MLIT compliance models are merely lagging indicators of physical reality. They act as historical archives rather than live controllers, making them fundamentally incapable of orchestrating real-time, deterministic logistics or supporting API-driven algorithmic dispatch.

> 現在のMLITによるBIM/CIMガイドラインが抱える根本的なアーキテクチャ上の脆弱性は、漸進的なLOD（詳細度：Level of Development）を通じた空間ジオメトリと資産属性のみに、排他的かつ狭視的な重点を置いている点にございます。LOD 300または400のモデルは、3次元物理空間（$x, y, z$）においてミリメートル単位の精度を提供いたしますが、時間次元（$t$）においては完全にゼロの解像度しか持ち合わせておりません。これは**「時間的データ減衰（Temporal Data Decay）」**と呼ばれる致命的なシステム障害を引き起こします。
> 
> 現場監督が17:00に従来のBIMファイルや日次スケジュールを手動で更新した瞬間から、そのデータの減衰は始まります。翌朝08:00の時点で、現場（Genba）の物理的なグラウンド・トゥルース（真実のデータ）は、確率論的な変動要因（急な天候変化、コンクリート養生の微小な遅れ、予期せぬサプライチェーンの遅延など）により、すでにデジタルツインから乖離（デシンクロ）しているのです。その結果、いかに高精細なジオメトリモデルであっても、「2024年物流問題」の解決においては完全に機能不全に陥ります。
> 
> 厳密な待ち行列理論（Queueing Theory）の観点から検証いたしますと、到着予定の物流ベクトル（例：10トンのコンクリートアジテータトラック）が、荷降ろし用ステージングゾーンの空き状況を従来のBIMモデルに自動クエリした場合、データベースは陳腐化した状態変数（Stale State Variable / 例：前日の入力に基づきゾーンが空いているという誤った仮定）を返します。トラックが到着し、その物理的空間が待機中のクレーンによって占有されていることを発見した瞬間、スレッドをブロックする待機列が即座に生成されます。これにより、物理的な物流資産は非最適化された待機状態に強制され、ディーゼル燃料を浪費し、厳格なSLAの納品枠を破壊し、サプライチェーン全体に遅延（レイテンシ）を連鎖させることになります。
> 
> ゆえに、従来のMLIT準拠モデルは物理的現実の「遅行指標」に過ぎません。それらは生きたコントローラーではなく歴史的アーカイブとして機能するため、リアルタイムで決定論的な物流をオーケストレーションすることや、API主導のアルゴリズムによる配車をサポートすることは、原理的に不可能なのでございます。

---


