<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Digital Twins</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/digital-twins/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/digital-twins/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>デジタルツインの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>IoT・グラフデータモデルの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>DTDL（Digital Twins Definition Language）の基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>物理空間・設備をデジタルでモデル化したいソリューションアーキテクト</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Digital Twinsの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>スマートビルディング・スマートファクトリーを構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Digital Twinsとは？<br>2. 主要構成要素<br>3. ユースケース<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Digital Twinsとは？</p></div>

建物・工場・都市・サプライチェーンなど現実世界の環境を<strong>知識グラフとしてモデル化するIoTプラットフォーム</strong>です。
モノ・場所・人・プロセス間の関係性をデジタルツインとして表現し、IoTデバイスからのリアルタイムデータと組み合わせて全体最適化や予測分析を行えます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">オープンモデリング言語（DTDL）：</span>業界標準のJSON-LDベースの言語でカスタムのツインモデルを定義できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">知識グラフ：</span>建物の階層構造や設備同士の関係性をノードとエッジで柔軟に表現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">リアルタイムデータ同期：</span>IoT Hub等と連携しセンサーデータでツインの状態を常に最新に保ちます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">クエリAPI：</span>SQLライクなクエリ言語でグラフ内の複雑な関係性を検索・分析できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. 主要構成要素</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">要素</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>モデル</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">DTDLで定義されたエンティティの種類（部屋・センサー・設備等）</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ツイン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">モデルに基づき作成された現実世界の個々のオブジェクトのデジタル表現</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>リレーションシップ</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ツイン間の関係（「含む」「隣接する」等）を表すグラフのエッジ</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ルート（Route）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">イベントをEvent Hubs等の外部エンドポイントへ転送する設定</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. ユースケース</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">分野</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">活用例</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>スマートビルディング</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">空調・照明の最適化、占有率に基づくエネルギー管理</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>製造業</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">生産ラインのデジタルツイン化による稼働監視・最適化</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>スマートシティ</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">交通流・インフラ設備の都市全体モデリング</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">業界標準モデル：</span>RealEstateCoreなどオープンな業界標準オントロジーを活用しモデリングを加速できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">3D Scenes Studio：</span>3D空間モデルとデジタルツインを紐づけた可視化ビューアを提供します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Functions連携：</span>イベントルートをトリガーにカスタムロジックを実行できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Microsoft Entra ID統合：</span>細かなロールベースアクセス制御により安全にグラフを管理できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>操作（API呼び出し）：</strong>ツイン・リレーションシップの作成/更新/クエリ等のAPI操作回数に基づく従量課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>メッセージ：</strong>イベントルート経由で送信されたメッセージ数に基づく課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>関連リソース：</strong>連携するIoT Hub・Event Hubs・Functions等は別途課金されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/digital-twins/
https://azure.microsoft.com/ja-jp/pricing/details/digital-twins/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Digital Twinsは<strong>現実世界を知識グラフとしてモデル化するIoTプラットフォーム</strong>です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>DTDL</strong>によりカスタムのツインモデルと関係性を柔軟に定義できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>スマートビルディング・製造業・スマートシティなど<strong>幅広い業界</strong>で活用されています。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>3D Scenes Studio</strong>により直感的な空間可視化を実現できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
