<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Functions</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Microsoft Azure Functions) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/azure-functions/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/azure-functions/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>サーバーレス・FaaS（Function as a Service）の基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>イベント駆動アーキテクチャの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>1つ以上のプログラミング言語（C#・Python・JavaScriptなど）の基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>イベント駆動の軽量処理を実装したいアプリケーション開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Functionsの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>サーバー管理不要でコスト効率の良い処理基盤を構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Functionsとは？<br>2. ホスティングプラン<br>3. トリガーとバインディング<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Functionsとは？</p></div>

イベントに応じて小さなコード片（関数）を実行する<strong>サーバーレスコンピューティングサービス</strong>です。
インフラのプロビジョニングや管理を意識せずに、HTTPリクエスト・タイマー・メッセージキュー・データベース変更など多様なトリガーに応じてコードを実行できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動スケール：</span>実行されたイベント数に応じてインスタンスを自動的に増減し、未使用時はゼロまでスケールダウンします。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">豊富なトリガー：</span>HTTP・Timer・Blob Storage・Queue Storage・Event Hubs・Cosmos DBなど多様なトリガーをサポートします。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マルチ言語対応：</span>C#・JavaScript/TypeScript・Python・Java・PowerShellに対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Durable Functions：</span>ステートフルなワークフローやファンアウト/ファンイン処理をコードで定義できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. ホスティングプラン</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">プラン</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>従量課金（Consumption）プラン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">実行時のみ課金、ゼロへの自動スケールダウン、最大実行時間あり。完全サーバーレス。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Flex Consumptionプラン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">従量課金の柔軟性に加え、VNet統合や常時インスタンスの予約が可能。</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Premiumプラン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">コールドスタート回避（事前ウォーム済みインスタンス）、VNet統合、長時間実行に対応。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>App Service（専用）プラン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">既存のApp Serviceプラン上で常時稼働。予測可能な負荷向け。</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. トリガーとバインディング</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">種類</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">例</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>HTTPトリガー</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">REST API・Webhookエンドポイントの実装</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Timerトリガー</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">CRON式によるスケジュール実行（バッチ処理等）</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Blob/Queueトリガー</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ファイルアップロード時の処理、非同期メッセージ処理</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Cosmos DB/Event Hubsトリガー</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">データ変更フィード処理、ストリーミングデータ処理</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Durable Functions：</span>オーケストレーター関数によりステートフルなワークフロー・チェーン処理・ファンアウト/ファンインパターンを実装できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Logic Apps連携：</span>コードレスのワークフロー自動化とシームレスに統合できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Functions Core Tools：</span>ローカル開発・デバッグ・デプロイ用のCLIツールセットです。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Application Insights連携：</span>関数の実行ログ・パフォーマンス・エラーをリアルタイムに監視できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>従量課金プラン：</strong>実行回数（100万回まで無料枠あり）と実行時間（GB秒）に基づく課金。未実行時は完全無料。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Premiumプラン：</strong>事前ウォームインスタンス数とvCPU/メモリに基づく時間課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>App Serviceプラン：</strong>既存のApp Serviceプラン料金内で実行（追加課金なし）。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/azure-functions/
https://azure.microsoft.com/ja-jp/pricing/details/functions/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Functionsは<strong>サーバーレスのイベント駆動コンピューティングサービス</strong>。インフラ管理不要で軽量処理を実行できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>従量課金プランは未実行時に無料</strong>。コスト効率の高いアーキテクチャを実現できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Durable Functions</strong>により複雑なステートフルワークフローもコードで表現できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ワークロードの特性に応じて<strong>4種類のホスティングプラン</strong>から最適なものを選べます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
