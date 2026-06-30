<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Pipelines</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/devops/pipelines/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/devops/pipelines/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>CI/CD（継続的インテグレーション/デリバリー）の基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>YAML記法の基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Gitバージョン管理の基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ビルド・テスト・デプロイを自動化したい開発者・DevOpsエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Pipelinesの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>マルチプラットフォーム/マルチクラウドへのデプロイパイプラインを構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Pipelinesとは？<br>2. パイプラインの構成要素<br>3. エージェントの種類<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Pipelinesとは？</p></div>

コードのビルド・テスト・デプロイを自動化する<strong>クラウドベースのCI/CDサービス</strong>です（Azure DevOpsを構成するサービスの1つ）。
あらゆる言語・プラットフォームに対応し、Linux・macOS・Windowsを横断したマルチプラットフォームビルドや、任意のクラウド（Azure・AWS・GCP）へのデプロイを自動化できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">YAMLパイプライン：</span>パイプライン定義をコードとして管理し、リポジトリでバージョン管理できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マルチステージパイプライン：</span>ビルド・テスト・複数環境（開発/ステージング/本番）へのデプロイを単一の定義で表現できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">幅広い言語/フレームワーク対応：</span>.NET・Java・Node.js・Python・コンテナなど多様な技術スタックに対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">承認とゲート：</span>本番環境へのデプロイ前に手動承認やポリシーチェックを挿入できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. パイプラインの構成要素</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">要素</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ステージ（Stage）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">パイプラインを論理的に分割した大きな単位（ビルド・デプロイ等）</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ジョブ（Job）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">単一のエージェント上で実行されるタスクのまとまり</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ステップ（Step）/タスク（Task）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">スクリプト実行やビルド等の最小単位の処理</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>トリガー</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">コードのプッシュ・プルリクエスト・スケジュールに基づく自動実行条件</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. エージェントの種類</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">種類</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Microsoftホステッドエージェント</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Microsoftが管理するクリーンなビルド環境（Linux/Windows/macOS）をジョブごとに自動プロビジョニング</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>セルフホステッドエージェント</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">自社で管理するマシン/VMにエージェントを導入し、カスタムツールや高い制御が必要な場合に利用</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">環境（Environments）：</span>デプロイ先のターゲット（Kubernetes・VM等）の状態とデプロイ履歴を追跡管理します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">テンプレート：</span>共通のパイプラインロジックを再利用可能なテンプレートとして複数プロジェクトで共有できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">GitHub Actions連携：</span>GitHubリポジトリのコードに対してもAzure Pipelinesを利用したビルド/デプロイが可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">テスト結果の統合表示：</span>ユニットテスト・コードカバレッジの結果をパイプライン実行画面で可視化します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Microsoftホステッド並列ジョブ：</strong>パブリックプロジェクトは無料、プライベートプロジェクトは1つの無料並列ジョブ（月1,800分まで）が付属し、追加ジョブは月額課金です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>セルフホストエージェント：</strong>無制限の並列ジョブが無料で利用可能ですが、エージェントを実行するインフラ費用は別途必要です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>OSS（オープンソース）プロジェクト：</strong>パブリックリポジトリには無料の並列ジョブが提供されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/devops/pipelines/
https://azure.microsoft.com/ja-jp/pricing/details/devops/azure-pipelines/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Pipelinesは<strong>クラウドベースのCI/CDサービス</strong>。あらゆる言語・プラットフォームに対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>YAMLパイプライン</strong>によりCI/CD定義をコードとしてバージョン管理できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Microsoftホステッド/セルフホステッド</strong>のエージェントを使い分けることができます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>OSSのパブリックプロジェクトは<strong>無料の並列ジョブ</strong>を活用できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
