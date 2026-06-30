<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Virtual Machines</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Microsoft Azure Virtual Machines) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/virtual-machines/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/virtual-machines/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>仮想化・IaaS（Infrastructure as a Service）の基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure サブスクリプション・リソースグループの基本知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ネットワークの基礎知識（VNet・NSG・パブリック/プライベートIP）</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>クラウド上にサーバーインフラを構築するインフラエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Machinesの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>オンプレミスからのクラウド移行（リフト＆シフト）を検討する方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Virtual Machinesとは？<br>2. VMシリーズと主な構成要素<br>3. デプロイ・管理方法<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Virtual Machinesとは？</p></div>

Linux・Windows Server・SQL Server・Oracle・SAPなど幅広いOSとソフトウェアをサポートする<strong>オンデマンドのスケーラブルなコンピューティングリソース</strong>を提供するAzureのIaaSサービスです。
物理ハードウェアの調達・保守を必要とせず、必要な時に必要な分だけ仮想マシンを起動・停止・スケールできる柔軟性が特長です。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">幅広いOS/ソフトウェア対応：</span>Windows Server・各種Linuxディストリビューション・SQL Server・SAPなどのイメージをMarketplaceから選択してデプロイできます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">柔軟なスケーリング：</span>Virtual Machine Scale Sets（VMSS）により負荷に応じてインスタンス数を自動的に増減できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高可用性：</span>可用性ゾーン・可用性セットを使用してデータセンター障害やラック障害からアプリケーションを保護します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">コンフィデンシャルコンピューティング：</span>AMD SEV-SNPやIntel TDXを利用したコンフィデンシャルVMにより使用中のデータをハードウェアレベルで保護します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. VMシリーズと主な構成要素</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">シリーズ系統</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴・用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>汎用（D・B・Aシリーズ）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">CPU・メモリ・ストレージのバランスが取れた構成。Webサーバーや中小規模データベース、開発・テスト環境に最適。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>コンピューティング最適化（Fシリーズ）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">高いCPU対メモリ比率。バッチ処理・ゲームサーバー・分析ワークロード向け。</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>メモリ最適化（Eシリーズ・Mシリーズ）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">大容量メモリを搭載。リレーショナルデータベース・大規模インメモリ処理（SAP HANA等）に対応。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>GPU（NCシリーズ・NDシリーズ等）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">機械学習・AIトレーニング・グラフィックスレンダリング向けのGPUアクセラレーション。</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ストレージ最適化（Lシリーズ）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">高いディスクスループットとIOPS。NoSQLデータベースやビッグデータワークロード向け。</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. デプロイ・管理方法</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">方法</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">概要</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Azure Portal</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">GUIベースでVMの作成・設定・監視を行う標準的な管理画面。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Azure CLI / PowerShell</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">コマンドラインからVMをスクリプトで自動作成・管理。</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ARMテンプレート / Bicep</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Infrastructure as Codeによる宣言的なリソースデプロイ。</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Azure Resource Manager API</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">REST API経由でVMライフサイクルをプログラムから制御。</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Managed Disks：</span>ディスクの可用性・管理をAzureが自動化。Premium SSD・Standard SSD・Standard HDD・Ultra Diskから選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Spot Virtual Machines：</span>未使用キャパシティを大幅割引で利用可能。中断可能なバッチ処理やテスト環境に最適です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">予約インスタンス（Reserved Instances）：</span>1年または3年の事前コミットメントによりオンデマンド料金より大幅に節約できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Hybrid Benefit：</span>既存のWindows ServerやSQL Serverライセンスを持ち込み、ライセンスコストを削減できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>従量課金制：</strong>VMの稼働時間（分単位）に対して、選択したシリーズ・サイズ・OS・リージョンに応じた料金が発生します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>停止（割り当て解除）時：</strong>「停止済み（割り当て解除済み）」の状態であればコンピューティング料金は発生しません（ディスク料金は継続）。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>追加コスト：</strong>Managed Disks・パブリックIP・帯域幅（エグレス）などは別途課金されます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>割引オプション：</strong>予約インスタンス（最大72%節約）・Azure Spot VM（最大90%節約）・Azure Hybrid Benefitが利用可能です。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/virtual-machines/
https://azure.microsoft.com/ja-jp/pricing/details/virtual-machines/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Machinesは<strong>柔軟なIaaS型コンピューティングサービス</strong>。幅広いOS・ソフトウェアをオンデマンドでデプロイできます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ワークロードに応じた<strong>多様なVMシリーズ</strong>から最適な構成を選択することがコストとパフォーマンスの鍵です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>予約インスタンスやSpot VM</strong>を活用することで大幅なコスト削減が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Azure Hybrid Benefit</strong>により既存のライセンス資産を有効活用できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
