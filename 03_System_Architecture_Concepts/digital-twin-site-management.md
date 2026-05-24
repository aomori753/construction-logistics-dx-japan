<div align="center">
  <h1>Digital Twin Site Management</h1>
  <h3>デジタルツイン現場管理：「現場」の再設計とイベント駆動型アーキテクチャ</h3>
</div>

<br>

> **Metadata:**
> * **Document ID:** `MOD-03-01-DIGITAL-TWIN`
> * **Status:** 🏗️ Active Specification / 仕様確定
> * **Author:** Jericho Ong / ジェリコ・オング (Construction & Logistics DX Independent Researcher)
> * **Language:** English / Japanese (Advanced Technical Business / ビジネス技術日本語)

---

## Executive Summary / 概要

In contemporary construction technology, the term "Digital Twin" is frequently misapplied as a synonym for 3D BIM/CIM (Building Information Modeling). However, from a Systems Engineering perspective, a static 3D model is merely a high-latency spatial database. A true Digital Twin is a **Cyber-Physical State Machine**—an event-sourced architecture that continuously synchronizes the stochastic physical reality of the site (*Ground Truth*) with the cloud architecture via high-frequency telemetry. 

This document outlines the architectural transition of traditional, asynchronous site management into a deterministic, Pub/Sub IT infrastructure governed by Hybrid Automata theory.

> 現代の建設テクノロジーにおいて、「デジタルツイン」という用語はしばしば静的な3D BIM/CIM（ビルディング・インフォメーション・モデリング）の同義語として誤用されております。しかし、システムエンジニアリングの観点から見れば、静的な3Dモデルはレイテンシ（遅延）の高い単なる空間データベースに過ぎません。真のデジタルツインとは**「サイバーフィジカル・ステートマシン（状態遷移機械）」**であり、高頻度のテレメトリーを介して、確率論的な現場の物理的現実（グラウンド・トゥルース）とクラウド・アーキテクチャを継続的に同期させるイベントソーシング型アーキテクチャでございます。
> 
> 本ドキュメントでは、従来の非同期的な現場管理を、ハイブリッド・オートマトン理論によって制御される、決定論的なPub/Sub（パブリッシュ・サブスクライブ）ITインフラストラクチャへと移行させるためのアーキテクチャの青写真を描き出します。

---

## 1. The Fallacy of Static BIM / 静的BIMの誤謬とイベントソーシングへの移行

The fundamental flaw in current Construction DX initiatives is the reliance on asynchronous CRUD (Create, Read, Update, Delete) databases. A BIM model that is updated manually at the end of a shift ($t + 12$ hours) possesses massive data latency. During that 12-hour blind spot, the digital twin does not reflect the physical reality of the site. If a logistics vector (a concrete agitator truck) relies on a static BIM model to determine unloading zone availability, the system will inevitably generate thread-blocking queues—the core mechanism of the 2024 Problem.

To achieve Enterprise-grade DX, the Digital Twin must utilize an **Event-Sourced Architecture**. Instead of overriding data in a static table, every physical movement, payload drop, and machine activation on site is recorded as an immutable log event in a time-series stream.

> 現在の建設DXにおける根本的な欠陥は、非同期のCRUD（作成・読み取り・更新・削除）データベースへの依存にございます。シフトの終わりに手動で更新されるBIMモデル（$t + 12$時間）は、巨大なデータ遅延を抱えています。その12時間のブラインドスポットにおいて、デジタルツインは現場の物理的現実を反映しておりません。もし物流ベクトル（アジテータトラックなど）が、荷降ろしゾーンの空き状況を判断するために静的なBIMモデルに依存した場合、システムは必然的にスレッドをブロックする待機列（2024年問題の中核的メカニズム）を生成いたします。
> 
> エンタープライズレベルのDXを達成するためには、デジタルツインは**イベントソーシング・アーキテクチャ**を利用しなければなりません。静的なテーブルのデータを上書きするのではない、現場でのあらゆる物理的動作、資材の配置、および重機の稼働を、時系列ストリームにおける「不変のログイベント」として記録するのです。

---

## 2. Transitioning from Asynchronous Polling to Event-Driven Pub/Sub / 非同期ポーリングからイベント駆動型Pub/Subへの移行

To successfully map civil engineering to IT systems, the architecture must eliminate legacy data synchronization methods. 

Traditional construction sites operate on **low-frequency batch updates** or manual schedule polling (e.g., daily schedule distribution or manual radio checks). In systems architecture terms, this acts as a localized, high-latency database prone to severe desynchronization between logistics nodes and the physical site.

A true Cyber-Physical System replaces this manual polling mechanism with a **Distributed Message Broker** (e.g., Apache Kafka). Heavy machinery and logistics nodes constantly *publish* their spatial coordinates and kinematic states. Sub-contractors, site managers, and incoming delivery trucks *subscribe* to these event streams, receiving zero-latency spatial updates asynchronously without requesting them.

> 土木工学をITシステムに適切にマッピングするためには、アーキテクチャから旧来のデータ同期手法を排除しなければなりません。
> 
> 従来の建設現場は、**低頻度のバッチ更新**や手動のスケジュール・ポーリング（日々のスケジュール配布や無線による手動確認など）で稼働しています。システムアーキテクチャの観点から見ると、これは物流ノードと物理的な現場との間に深刻な非同期化（デシンクロ）を引き起こしやすい、レイテンシの高いローカル・データベースとして機能します。
> 
> 真のサイバーフィジカルシステムは、この手動のポーリングメカニズムを**分散型メッセージブローカー**（Apache Kafkaなど）に置き換えます。重機や物流ノードは、自身の空間座標や運動状態を常に「パブリッシュ（発行）」します。協力会社、現場監督、および到着予定の配送トラックはこれらのイベントストリームを「サブスクライブ（購読）」し、リクエストを送信することなく、空間的な更新情報を非同期かつゼロレイテンシで受け取るのです。

---

## 3. The Hybrid Automata Execution Pipeline / ハイブリッド・オートマトン実行パイプライン

To transition the site from stochastic chaos to deterministic predictability, the Digital Twin utilizes the Hybrid Automata Model defined in CPAL. Continuous physical variables (GPS coordinates) trigger discrete state transitions within the cloud infrastructure.

Given a spatial zone $Z_1$, the discrete state transition function $R$ is triggered by an edge-telemetry event $e$:

$$q_{t+1} = R(q_t, e) \quad \text{where} \quad e \in \text{Kafka Topic: } \texttt{site.telemetry.zone1}$$

If a crane enters a geofenced lift zone, the continuous physical coordinate breaches the boundary invariant ($\text{Inv}$), triggering a discrete state shift from `STATE_IDLE` to `STATE_LIFT_ACTIVE`. This state change propagates through Kafka, instantly locking the zone and rerouting any incoming delivery trucks via Just-In-Time API webhooks.

> 現場を確率論的な混沌から決定論的な予測可能性へと移行させるため、デジタルツインはCPALで定義された「ハイブリッド・オートマトン・モデル」を利用します。連続的な物理変数（GPS座標など）が、クラウドインフラ内での離散的な状態遷移をトリガーします。
> 
> 空間ゾーン $Z_1$ において、離散状態遷移関数 $R$ は、エッジ・テレメトリー・イベント $e$ によってトリガーされます。クレーンがジオフェンスで囲まれた吊り上げゾーンに進入すると、連続的な物理座標が境界不変条件（$\text{Inv}$）を破り、`STATE_IDLE`（待機）から `STATE_LIFT_ACTIVE`（吊り上げ稼働中）への離散的な状態シフトがトリガーされます。この状態変化はKafkaを通じて伝播し、即座に該当ゾーンをロックダウンさせ、JIT（ジャスト・イン・タイム）APIのWebhookを介して到着予定のトラックを別ルートへ誘導（リルート）いたします。

---

## 4. Cyber-Physical State Machine Topology / サイバーフィジカル・ステートマシン・トポロジー

The following topology dictates how physical asset behaviors are serialized into digital events, processed by the Twin, and utilized to algorithmically control site logistics without human intervention.

> 以下のトポロジーは、物理的資産の挙動がどのようにデジタルイベントにシリアライズされ、デジタルツインによって処理され、人間の介入なしにアルゴリズムによって現場の物流を制御するかを規定するものでございます。

```mermaid
graph TD
    subgraph Physical_Layer ["Physical Ground Truth (Genba) / 物理的現実（現場）"]
        Crane["Tower Crane 01<br>(Load Active)"]
        Truck["Delivery Vector<br>(Approaching Gate)"]
        Zone["Staging Area B<br>(Occupied)"]
    end

    subgraph IoT_Edge_Network ["Edge Telemetry Layer / エッジ・テレメトリー層"]
        RTK["RTK GNSS Sensors (WGS84)"]
        Load["Crane Load Cells / IMUs"]
        TPM["TPM 2.0 Secure Boot"]
    end

    subgraph Cyber_Layer ["Digital Twin Event Architecture / デジタルツイン・イベント層"]
        Kafka["Apache Kafka<br>(Event Stream Broker)"]
        State["Redis Enterprise<br>(In-Memory State Machine)"]
        PostGIS["PostGIS Spatial DB<br>(Dynamic Geofences)"]
    end

    Crane -->|Mechanical Telemetry| Load
    Truck -->|Spatial Coordinates| RTK
    
    Load --> TPM
    RTK --> TPM
    
    TPM ===>|mTLS ECDSA Signed Payload| Kafka
    
    Kafka --> State
    Kafka --> PostGIS
    
    State -.->|Asynchronous API Webhook| Truck
    PostGIS -.->|Update RCC8 Bounding Box| Zone
