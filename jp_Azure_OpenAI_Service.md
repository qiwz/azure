<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure OpenAI Service</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/ai-services/openai/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/ai-services/openai/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>大規模言語モデル（LLM）・生成AIの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>プロンプトエンジニアリングの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>REST API・トークンベース課金の基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>生成AI機能を企業システムに組み込みたいアプリケーション開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure OpenAI Serviceの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>エンタープライズ要件下でOpenAIモデルを安全に利用したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure OpenAI Serviceとは？<br>2. 提供モデルファミリー<br>3. デプロイタイプ<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure OpenAI Serviceとは？</p></div>

OpenAIの最先端の言語モデル・推論モデル・画像生成モデルを、Azureのセキュリティ・コンプライアンス・エンタープライズ機能と組み合わせて利用できる<strong>マネージドAIサービス</strong>です。
GPTシリーズなどのモデルをREST API経由で呼び出し、チャットボット・要約・コード生成・検索拡張生成（RAG）など幅広いユースケースに活用できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">エンタープライズグレードのセキュリティ：</span>VNet統合・プライベートエンドポイント・Microsoft Entra ID認証によりデータを保護します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">独自データとの連携（On Your Data）：</span>Azure AI SearchなどとRAG構成を組み、自社データに基づく回答生成が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ファインチューニング：</span>対応モデルを独自データセットで微調整し、特定タスクの精度を向上できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">コンテンツフィルタリング：</span>有害・不適切なコンテンツの入出力を自動的に検出・ブロックします。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. 提供モデルファミリー</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">モデル系統</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>GPTシリーズ</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">テキスト生成・対話・要約・コード生成などの汎用言語モデル</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>推論（Reasoning）モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">複雑な多段階推論や数学・コーディング問題向けに最適化されたモデル</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>画像生成モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">テキストプロンプトから画像を生成するモデル</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>音声モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">音声からテキスト・テキストから音声への変換モデル</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>埋め込み（Embeddings）モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">テキストをベクトル化し意味検索・RAGの基盤として利用</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. デプロイタイプ</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">タイプ</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>従量課金（Pay-as-you-go / Global Standard等）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">トークン使用量に応じた課金。柔軟な利用に最適</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>プロビジョニング済みスループット（PTU）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">専用キャパシティを事前確保し安定したレイテンシ・スループットを保証</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>バッチ（Batch）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">非同期で大量リクエストを低コストに処理</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure AI Foundry連携：</span>モデルの評価・プロンプトフロー設計・エージェント構築を統合開発環境で行えます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">関数呼び出し（Function Calling）：</span>モデルが外部APIやツールを呼び出すエージェント的な振る舞いを実装できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マルチモーダル対応：</span>テキストに加え画像・音声入力を扱えるモデルも提供されています。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">責任あるAI監視：</span>乱用検出・コンテンツフィルターのカスタマイズによりガバナンスを強化できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>従量課金：</strong>入力/出力トークン数（1,000トークン単位）に基づく課金。モデルの種類・サイズにより単価が大きく異なります。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>PTU（プロビジョニング済み）：</strong>確保したスループット単位（PTU数）に基づく時間課金。大規模・安定運用向け。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ファインチューニング：</strong>トレーニング時間とトレーニング済みモデルのホスティングにそれぞれ別途課金が発生します。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/ai-services/openai/
https://azure.microsoft.com/ja-jp/pricing/details/cognitive-services/openai-service/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure OpenAI Serviceは<strong>OpenAIの最先端モデルをエンタープライズ要件下で利用できるマネージドAIサービス</strong>です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>言語・推論・画像・音声・埋め込み</strong>など多様なモデルファミリーを単一サービスから利用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>用途に応じて<strong>従量課金とPTU</strong>を使い分けることでコストとパフォーマンスを最適化できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>VNet統合・コンテンツフィルター</strong>などにより安全性とガバナンスを確保できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
