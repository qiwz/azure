<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure DNS</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/dns/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/dns/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>DNSの基本概念（Aレコード・CNAME・MX等）</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ドメイン名・名前解決の仕組みの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Networkの基本概念</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ドメイン名のホスティング・名前解決基盤を管理するインフラエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure DNSの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>VNet内のプライベート名前解決基盤を構築したい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure DNSとは？<br>2. ゾーンの種類<br>3. 対応レコードタイプ<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure DNSとは？</p></div>

Microsoft Azureのインフラ上でDNSドメインをホストする<strong>高可用性・高性能なDNSホスティングサービス</strong>です。
Azureの既存ツール・APIs・課金体系・サポート体制を使用してドメインを管理でき、グローバルなエニーキャストネットワークにより高速な名前解決を実現します。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高い可用性と性能：</span>世界中のエニーキャストネームサーバーにより低レイテンシな名前解決を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azureリソースとの統合管理：</span>Azure Portal・CLI・PowerShell・ARMテンプレートでDNSレコードを一元管理できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">プライベートDNSゾーン：</span>VNet内限定の名前解決を提供し、オンプレミスにはないクラウド専用ドメインを管理できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">エイリアスレコード：</span>Azureリソース（パブリックIP・Traffic Manager等）への参照を動的に自動更新します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. ゾーンの種類</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">種類</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>パブリックDNSゾーン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">インターネット上から問い合わせ可能な一般公開ドメインを管理</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>プライベートDNSゾーン</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">1つ以上のVNetにリンクし内部限定の名前解決を提供</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. 対応レコードタイプ</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">レコードタイプ</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>A / AAAA</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ホスト名をIPv4/IPv6アドレスへマッピング</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>CNAME</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">別名から正規ホスト名への参照</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>MX / TXT / SRV</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">メール配送・ドメイン検証・サービス検出用レコード</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>NS / SOA</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ゾーン委任と権威情報を定義する管理用レコード</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">自動登録：</span>プライベートDNSゾーンでVM作成時にレコードを自動登録・削除できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">DNSセキュリティポリシー：</span>悪意あるドメインへの問い合わせをフィルタリングし内部からの脅威通信を防止します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure RBAC統合：</span>ゾーン・レコードセット単位できめ細かなアクセス制御が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高いSLA：</span>パブリックDNSゾーンは100%の可用性SLAを提供します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ホストされるゾーン：</strong>ゾーン単位の月額固定料金が発生します（一定数までは比較的安価）。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>DNSクエリ：</strong>受信したDNSクエリ数（100万回単位）に応じた従量課金が発生します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>プライベートDNSゾーン：</strong>ゾーン課金に加え、VNetリンク数に応じた料金体系が適用されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/dns/
https://azure.microsoft.com/ja-jp/pricing/details/dns/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure DNSは<strong>高可用性・高性能なDNSホスティングサービス</strong>。パブリック/プライベート両方のドメインを管理できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>プライベートDNSゾーン</strong>によりVNet内限定の名前解決基盤を簡単に構築できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>エイリアスレコード</strong>を使えばAzureリソースのIP変更にも自動的に追従できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azureの<strong>既存管理ツール・RBAC</strong>と統合されているため運用負荷を抑えられます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
