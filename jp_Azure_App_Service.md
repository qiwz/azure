<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure App Service</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Microsoft Azure App Service) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/app-service/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/app-service/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>PaaS（Platform as a Service）の基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Webアプリケーション開発の基礎知識（.NET・Node.js・Python・Javaなど）</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>CI/CDの基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Webアプリ・APIをクラウド上にデプロイしたいアプリケーション開発者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure App Serviceの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>インフラ管理の負荷を軽減してアプリ開発に集中したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure App Serviceとは？<br>2. App Service プラン（料金レベル）<br>3. 対応言語・デプロイ方法<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure App Serviceとは？</p></div>

Webアプリ・REST API・モバイルバックエンドをホストするための<strong>フルマネージドPaaS（Platform as a Service）</strong>です。
基盤となるインフラ（OS・パッチ適用・ロードバランサーなど）の管理をAzureに任せ、開発者はコードのデプロイとアプリケーションロジックに集中できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マルチ言語対応：</span>.NET・Java・Node.js・Python・PHP・Rubyに加え、カスタムコンテナのデプロイもサポートします。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">組み込みのオートスケール：</span>CPU使用率やスケジュールに応じてインスタンス数を自動調整します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">デプロイスロット：</span>本番環境に影響を与えずにステージング環境でテストし、スワップでゼロダウンタイムデプロイを実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">組み込みのCI/CD連携：</span>GitHub・Azure DevOps・Bitbucketと連携して継続的デプロイを自動化します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. App Service プラン（料金レベル）</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">プラン</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Free / Shared</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">共有インフラ上で動作、カスタムドメイン不可</td><td style="border:1px solid #C7E0F4; padding:8px;">学習・検証用</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Basic</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">専用VM、手動スケール、カスタムドメイン対応</td><td style="border:1px solid #C7E0F4; padding:8px;">小規模本番ワークロード</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Standard</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">オートスケール・デプロイスロット（5個）・日次バックアップ</td><td style="border:1px solid #C7E0F4; padding:8px;">本番ワークロード</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Premium (v3)</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">高性能ハードウェア・デプロイスロット（20個）・VNet統合</td><td style="border:1px solid #C7E0F4; padding:8px;">高負荷・エンタープライズ用途</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Isolated (v2)</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">App Service Environment（ASE）専用ネットワーク分離</td><td style="border:1px solid #C7E0F4; padding:8px;">高セキュリティ・大規模エンタープライズ</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. 対応言語・デプロイ方法</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">カテゴリ</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">内容</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>対応言語/フレームワーク</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">.NET・Java・Node.js・PHP・Python・Ruby・静的サイト</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>コンテナ対応</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Web App for Containers（Linux/Windowsコンテナ）、Docker Compose（マルチコンテナ）</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>デプロイ方法</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Git・GitHub Actions・Azure DevOps Pipelines・ZIPデプロイ・FTP</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">App Service Environment（ASE）：</span>専用のネットワーク分離環境で実行する完全に隔離されたApp Serviceデプロイです。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">認証/認可（Easy Auth）：</span>Microsoft Entra ID・Google・Facebookなどのプロバイダーとコード不要で連携できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">VNet統合：</span>アプリからプライベートネットワーク内のリソースへ安全にアクセスできます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Application Insights連携：</span>パフォーマンス監視・分散トレーシング・異常検知を統合的に提供します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Free/Sharedティア：</strong>無料〜低価格で小規模な検証用途に利用可能（CPU/帯域に制限あり）。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>専用プラン（Basic〜Isolated）：</strong>App Serviceプランに割り当てたコンピューティングインスタンス（vCPU/メモリ）の時間課金制。同一プラン内で複数アプリを実行可能。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>割引オプション：</strong>予約インスタンス（1年・3年）やAzure Hybrid Benefitにより費用を削減できます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/app-service/
https://azure.microsoft.com/ja-jp/pricing/details/app-service/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure App Serviceは<strong>フルマネージドPaaS</strong>。インフラ管理不要でWebアプリ・APIをすばやくデプロイできます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>デプロイスロット</strong>を使えばゼロダウンタイムで安全にリリースできます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ワークロード規模に応じて<strong>Free〜Isolatedまで5段階のプラン</strong>から選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>GitHub Actionsなどとの<strong>CI/CD連携</strong>により開発からリリースまでを自動化できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
