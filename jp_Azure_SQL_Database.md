<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure SQL Database</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/azure-sql/database/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/azure-sql/database/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>リレーショナルデータベース・SQLの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Microsoft SQL Serverの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>DTU・vCoreなどデータベース性能指標の基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>マネージドなリレーショナルデータベースを構築したいデータベース管理者・開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure SQL Databaseの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>オンプレミスSQL Serverからのクラウド移行を検討する方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure SQL Databaseとは？<br>2. デプロイオプション<br>3. 購入モデルとサービスレベル<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure SQL Databaseとは？</p></div>

最新バージョンのSQL Serverエンジン上に構築された<strong>フルマネージドのリレーショナルデータベースPaaS</strong>です。
パッチ適用・バックアップ・高可用性などの運用管理をAzureが自動化し、開発者はスキーマ設計とアプリケーション開発に集中できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">組み込みの高可用性：</span>標準で99.99%以上のSLAを提供し、障害発生時は自動フェイルオーバーします。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動チューニング：</span>AIがクエリパフォーマンスを分析し、インデックスの自動作成・削除を提案・実行します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動バックアップ：</span>フル・差分・ログバックアップを自動取得し、任意の時点へのリストアが可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高度な脅威防止：</span>Microsoft Defender for SQLによる異常検知・脆弱性評価を提供します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. デプロイオプション</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">デプロイ形態</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Single Database</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">独立したリソースを持つ単一データベース。シンプルなアプリ向け</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Elastic Pool</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">複数のデータベースでリソースプールを共有しコストを最適化。マルチテナントSaaS向け</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Managed Instance</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">オンプレミスSQL Serverとほぼ完全な互換性を持つインスタンス全体のマネージド版</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. 購入モデルとサービスレベル</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">モデル/レベル</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>vCoreベース購入モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">vCPU数・メモリ・ストレージを個別に選択。コストの透明性が高くハイブリッド特典（AHB）も適用可能</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>DTUベース購入モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">CPU・メモリ・I/Oを統合した単一指標（DTU）でシンプルにサイジング</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>General Purpose</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">バランス型の汎用ワークロード向けサービスレベル</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Business Critical</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">高IOPS・低レイテンシ・複数同期レプリカによるミッションクリティカル向け</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Hyperscale</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">最大100TBまでの自動スケーリングストレージに対応する大規模向けレベル</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サーバーレスコンピューティング層：</span>使用量に応じて自動的にスケールし、アイドル時はコンピューティング課金を一時停止できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Hybrid Benefit：</span>既存のSQL Serverライセンス（Software Assurance付き）を持ち込みコストを削減できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Active Geo-Replication：</span>異なるリージョンに最大4つの読み取り可能なセカンダリを作成し災害対策を強化します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">透過的データ暗号化（TDE）：</span>保存データを標準で自動暗号化します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>vCoreモデル：</strong>選択したvCore数・メモリ・サービスレベル（General Purpose/Business Critical/Hyperscale）に基づく時間課金、加えてストレージ容量課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>DTUモデル：</strong>Basic/Standard/Premiumの各階層でDTU数に応じた固定料金プラン。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>割引オプション：</strong>予約容量（1年・3年）やAzure Hybrid Benefitにより最大80%程度のコスト削減が可能です。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/azure-sql/database/
https://azure.microsoft.com/ja-jp/pricing/details/azure-sql-database/single/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure SQL Databaseは<strong>フルマネージドのリレーショナルデータベースPaaS</strong>。運用負荷を抑えながらSQL Serverの機能を活用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>用途に応じて<strong>Single Database・Elastic Pool・Managed Instance</strong>から選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Hyperscale</strong>サービスレベルにより大規模データベースの自動スケーリングが実現できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Azure Hybrid Benefit</strong>と予約容量を組み合わせることで大幅なコスト削減が可能です。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
