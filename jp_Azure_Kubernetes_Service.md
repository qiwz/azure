<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Kubernetes Service (AKS)</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/aks/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/aks/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>コンテナ・Dockerの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Kubernetesの基礎知識（Pod・Deployment・Service・Namespace）</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Network・IAM（Microsoft Entra ID）の基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>コンテナ化されたアプリケーションを運用するインフラ・プラットフォームエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Kubernetes Serviceの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>マイクロサービスアーキテクチャをAzure上に構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. AKSとは？<br>2. クラスター構成とノードプール<br>3. ティアと管理オプション<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. AKSとは？</p></div>

コンテナ化されたアプリケーションのデプロイ・スケーリング・運用を簡素化する<strong>フルマネージドKubernetesサービス</strong>です。
Kubernetesコントロールプレーンの構築・パッチ適用・アップグレードをAzureが管理し、開発者はワーカーノードとアプリケーションの運用に集中できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">マネージドコントロールプレーン：</span>APIサーバー・etcdなどの管理基盤をAzureが運用し、可用性とアップグレードを保証します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">クラスターオートスケーラー：</span>Pod需要に応じてノード数を自動調整。Node Auto Provisioningによりさらに高度な最適化も可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">統合されたセキュリティ：</span>Microsoft Entra ID統合・Azure Policy・Microsoft Defender for Containersによる脅威検出に対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">複数ノードプール：</span>Linux/Windowsノードの混在、GPUノード、スポットノードプールなど用途別に分離して運用できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. クラスター構成とノードプール</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">構成要素</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>システムノードプール</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">CoreDNS・metrics-serverなど重要なシステムPodをホストする必須プール</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ユーザーノードプール</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">アプリケーションワークロード専用のプール。複数追加可能</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>スポットノードプール</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">未使用キャパシティを割引価格で利用。中断耐性のあるワークロード向け</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>仮想ノード（Virtual Nodes）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Azure Container Instances連携によりノード起動を待たずに高速にバーストスケール</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. ティアと管理オプション</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">ティア</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">内容</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Free</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">コントロールプレーン無料。SLA保証なし。開発・テスト向け</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Standard</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">99.95%のSLA保証、大規模クラスター対応、本番運用向け</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Premium</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">長期サポート（LTS）バージョンの利用が可能、ミッションクリティカル向け</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">AKS Automatic：</span>ベストプラクティスが組み込まれた設定をAzureが自動管理する、運用負荷を最小化したクラスター作成モードです。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">GitOps連携：</span>Flux/ArgoCDと連携した宣言的なデプロイメント管理に対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure CNI / Cilium：</span>高性能なネットワークプラグインとeBPFベースのネットワークポリシーを選択できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Monitor for containers：</span>クラスター・ノード・Podレベルのメトリクスとログを統合監視できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>コントロールプレーン：</strong>Freeティアは無料。Standard/Premiumティアはクラスターあたり時間単位の固定料金が発生します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ノード（コンピューティング）：</strong>ノードプールを構成する仮想マシン（Azure VM）の料金がそのまま課金されます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>その他のコスト：</strong>マネージドディスク・ロードバランサー・帯域幅などの関連リソースが別途課金されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/aks/
https://azure.microsoft.com/ja-jp/pricing/details/kubernetes-service/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>AKSは<strong>フルマネージドKubernetesサービス</strong>。コントロールプレーンの運用負荷をAzureに任せられます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>複数ノードプール</strong>を活用しシステム・ユーザー・スポットワークロードを柔軟に分離できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>用途に応じて<strong>Free/Standard/Premium</strong>の3ティアから選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>AKS Automatic</strong>によりベストプラクティスを組み込んだクラスターを素早く構築できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
