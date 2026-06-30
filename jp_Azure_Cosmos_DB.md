<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Cosmos DB</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/cosmos-db/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/cosmos-db/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>NoSQL・分散データベースの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>JSON・ドキュメント指向データモデルの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>結果整合性・パーティショニングの基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>グローバル分散・低レイテンシなアプリケーションを構築する開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Cosmos DBの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>MongoDB・Cassandra等のNoSQL基盤をマネージド化したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Cosmos DBとは？<br>2. 対応API<br>3. 整合性レベル<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Cosmos DBとは？</p></div>

グローバルに分散させて運用できる<strong>フルマネージドのNoSQL/リレーショナルマルチモデルデータベース</strong>です。
99.999%の可用性SLA、シングルケタミリ秒のレイテンシ、無制限の水平スケーラビリティを提供し、複数の整合性レベルから選択できる点が特長です。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">グローバル分散：</span>世界中の任意のAzureリージョンへワンクリックでデータを複製し、マルチリージョン書き込みにも対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マルチモデルAPI：</span>単一のサービスでドキュメント・キーバリュー・グラフ・列指向データモデルをサポートします。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動インデックス作成：</span>スキーマレスでありながら全プロパティを自動的にインデックス化し、クエリ設計の手間を削減します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">5段階の整合性レベル：</span>厳密な整合性から結果整合性まで、用途に応じてきめ細かく選択できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. 対応API</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">API</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">データモデル / 互換性</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>NoSQL API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Cosmos DBネイティブのドキュメントデータベースAPI（推奨）</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>MongoDB API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">既存のMongoDBドライバー・ツールと互換性のあるドキュメントDB</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Cassandra API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Apache Cassandra互換の列指向データベース</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Gremlin API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">グラフデータベース（ノード・エッジ）モデル</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Table API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Azure Table Storage互換のキーバリューストア</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>PostgreSQL API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Citus拡張によるリレーショナル・分散PostgreSQLモデル</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. 整合性レベル</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">レベル</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Strong</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">線形化された厳密な整合性。最新の書き込みを必ず読み取り可能</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Bounded Staleness</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">一定の遅延・バージョン差以内で整合性を保証</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Session（デフォルト）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">同一クライアントセッション内での読み取り一貫性を保証</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Consistent Prefix</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">書き込み順序を保った状態での読み取りを保証</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Eventual</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">最終的な整合性のみ保証。最も高いスループットと低レイテンシ</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サーバーレスモード：</span>断続的なトラフィックパターンに対し、実際に消費したリクエストユニット（RU）分のみ課金されます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動スケール（Autoscale）：</span>負荷に応じてスループット（RU/秒）を自動的に上下動させます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">変更フィード（Change Feed）：</span>データ変更をリアルタイムにストリーミングし、Azure Functionsなどと連携したイベント駆動処理を構築できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">統合ベクトル検索：</span>AIアプリケーション向けのベクトルインデックス・検索機能を組み込みでサポートします。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>プロビジョニング済みスループット：</strong>事前に確保したリクエストユニット（RU/秒）に対する課金。手動またはAutoscaleで設定。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>サーバーレス：</strong>実際に消費したRUに対する従量課金。トラフィックが断続的なワークロード向け。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ストレージ：</strong>保存データ量（GB単位）に応じた別枠の課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>無料利用枠：</strong>新規アカウントには一定期間無料のRU/ストレージ枠が提供されます（詳細は公式サイト参照）。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/cosmos-db/
https://azure.microsoft.com/ja-jp/pricing/details/cosmos-db/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Cosmos DBは<strong>グローバル分散対応のマルチモデルNoSQLデータベース</strong>。99.999%の可用性と低レイテンシを実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>6種類のAPI</strong>により既存のMongoDB・Cassandra等の資産を活かしたまま移行できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>5段階の整合性レベル</strong>からアプリケーション要件に応じた最適なバランスを選択できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>サーバーレス/Autoscale</strong>を活用することでコストを使用量に応じて最適化できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
