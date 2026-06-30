<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Database for PostgreSQL</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/postgresql/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/postgresql/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>リレーショナルデータベース・SQLの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>PostgreSQLの基礎知識（拡張機能・レプリケーション）</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure VNet・プライベートエンドポイントの基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>OSSのPostgreSQLをマネージドで運用したいデータベース管理者・開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Database for PostgreSQLの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>PostGIS等の拡張機能やAI連携を活用したいデータベース設計者</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Database for PostgreSQLとは？<br>2. デプロイモデル<br>3. コンピューティングティア<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Database for PostgreSQLとは？</p></div>

コミュニティ版PostgreSQLエンジンをベースにした<strong>フルマネージドリレーショナルデータベースPaaS</strong>です。
現行の提供形態は「Flexible Server」で、パッチ適用・バックアップ・高可用性などの運用作業をAzureが担いつつ、豊富な拡張機能やパラメータの細かな制御も可能です。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">PostgreSQLとの高い互換性：</span>標準のPostgreSQLクライアント・ドライバー・拡張機能（PostGIS等）をそのまま利用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ゾーン冗長高可用性：</span>可用性ゾーンをまたいだ同期スタンバイレプリカで高い耐障害性を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">pgvector対応：</span>ベクトル類似検索拡張機能をネイティブサポートし、AI/RAGアプリケーションに活用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動バックアップ：</span>1〜35日間の保持期間で自動バックアップを取得し、ポイントインタイムリストアに対応します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. デプロイモデル</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">モデル</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Flexible Server</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">きめ細かなパラメータ制御・ゾーン配置・コスト最適化（停止/開始）が可能な現行の推奨デプロイモデル</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Single Server（旧モデル）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">新規利用は非推奨でFlexible Serverへの移行が案内されている旧世代モデル</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Cosmos DB for PostgreSQL</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Citus拡張による水平分散・大規模分析向けの別サービス</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. コンピューティングティア</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">ティア</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Burstable</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">低コストで一時的な負荷増加に対応。開発・小規模ワークロード向け</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>General Purpose</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">CPU・メモリのバランスが取れた本番ワークロード向け標準ティア</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Memory Optimized</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">高いメモリ対CPU比率が必要なワークロード向け</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サーバー停止/開始：</span>開発・検証用サーバーを一時停止することでコンピューティング課金を止められます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">リードレプリカ：</span>読み取りワークロードを分散させるための非同期レプリカを複数作成できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">豊富な拡張機能：</span>PostGIS・pg_cron・pgvectorなど多数のPostgreSQL拡張機能を有効化できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Microsoft Entra ID認証：</span>パスワードレスでMicrosoft Entra IDを使った認証が可能です。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>コンピューティング：</strong>選択したティア（Burstable/General Purpose/Memory Optimized）とvCore数に基づく時間課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ストレージ：</strong>プロビジョニングしたディスク容量（GB）に対する課金で、必要に応じてオンラインで拡張可能。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>バックアップ：</strong>標準保持期間内のバックアップストレージは無料、それを超える容量や長期保持は追加課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>割引オプション：</strong>予約容量（1年・3年）の事前コミットメントによりコストを削減できます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/postgresql/
https://azure.microsoft.com/ja-jp/pricing/details/postgresql/flexible-server/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Database for PostgreSQLは<strong>OSS PostgreSQL互換のフルマネージドデータベース</strong>。豊富な拡張機能を活かせます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>現行の推奨デプロイモデルは<strong>Flexible Server</strong>で、柔軟なパラメータ制御とコスト最適化が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>pgvector対応</strong>によりAI/RAGアプリケーションのベクトル検索基盤としても活用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>サーバーの停止/開始</strong>機能により開発・検証環境のコストを抑制できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
