<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Virtual Network (VNet)</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/virtual-network/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/virtual-network/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ネットワークの基本概念（IPアドレス・サブネット・ルーティング）</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>TCP/IP・DNSの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ファイアウォール・セキュリティグループの基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure上にネットワーク基盤を設計・構築するネットワークエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Networkの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>複数リソース間のセキュアな通信基盤を構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Virtual Networkとは？<br>2. 主要構成要素<br>3. 接続オプション<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Virtual Networkとは？</p></div>

Azure上にプライベートなネットワーク空間を構築する<strong>基本的なネットワークインフラサービス</strong>です。
VM・App Service・データベースなどのAzureリソースを論理的に分離されたネットワーク内に配置し、相互に安全に通信させたり、インターネットやオンプレミス環境と接続したりできます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サブネット分割：</span>VNetをサブネットに分割し、ワークロードごとにネットワークセグメントを分離できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ネットワークセキュリティグループ（NSG）：</span>サブネットやNIC単位で許可/拒否ルールを設定しトラフィックを制御します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">VNetピアリング：</span>異なるVNet間をAzureバックボーン経由で低レイテンシ接続します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">プライベートエンドポイント：</span>PaaSサービス（Storage・SQL等）へVNet内のプライベートIPで安全にアクセスできます。</li>
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
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>サブネット</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">VNet内をCIDR範囲で分割した論理ネットワークセグメント</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ルートテーブル（UDR）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">トラフィックの経路をカスタム定義しNVAなどへ強制ルーティング</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ネットワークセキュリティグループ（NSG）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">5タプルベースのインバウンド/アウトバウンドフィルタリングルール</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Azure DNS統合</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">プライベートDNSゾーンによるVNet内名前解決</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. 接続オプション</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">方法</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>VNetピアリング</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">Azure内の複数VNet間を低レイテンシで接続</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>VPN Gateway</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">オンプレミスとのIPsec VPN接続</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ExpressRoute</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">専用線によるオンプレミスとの高帯域・低レイテンシ接続</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Virtual WAN</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">グローバルなネットワークトポロジを一元管理するハブ＆スポーク基盤</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サービスエンドポイント：</span>VNet内からPaaSサービスへAzureバックボーン経由で直接アクセスし、インターネット経路を回避します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Firewall連携：</span>VNet全体に適用可能なステートフルなファイアウォール・脅威インテリジェンスを提供します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">NSGフローログ：</span>トラフィックフローを記録し、Network Watcherでセキュリティ分析・トラブルシューティングが可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サービスタグ：</span>Azureサービスごとに定義されたIPプレフィックスグループを使いNSGルールを簡略化できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>VNet自体：</strong>VNet・サブネット・NSGの作成・利用は無料です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>VNetピアリング：</strong>送受信データ量（GB単位）に応じた課金が発生します（同一リージョン/異なるリージョンで単価が異なる）。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>データ転送（エグレス）：</strong>VNetからインターネットへのアウトバウンドデータ転送には標準のエグレス料金が適用されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/virtual-network/
https://azure.microsoft.com/ja-jp/pricing/details/virtual-network/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Networkは<strong>Azure上のプライベートネットワーク基盤</strong>。リソース間の安全な通信を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>サブネット・NSG</strong>によりネットワークセグメンテーションとトラフィック制御を細かく設計できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>VNetピアリング・VPN Gateway・ExpressRoute</strong>など多様な接続オプションでハイブリッド構成にも対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>VNet自体は<strong>無料</strong>で利用可能、課金は主にピアリングとデータ転送に発生します。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
