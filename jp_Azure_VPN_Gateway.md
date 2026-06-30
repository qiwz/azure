<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure VPN Gateway</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/vpn-gateway/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/vpn-gateway/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>VPN・IPsec/IKEの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Networkの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>BGP・ルーティングの基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>オンプレミスとAzureを安全に接続したいネットワークエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure VPN Gatewayの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>リモートワーク環境からのセキュアなアクセス基盤を検討する方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure VPN Gatewayとは？<br>2. 接続タイプ<br>3. SKU（ゲートウェイサイズ）<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure VPN Gatewayとは？</p></div>

オンプレミス環境とAzure Virtual Network間、またはAzure VNet同士の間に<strong>暗号化されたIPsec/IKE VPNトンネル接続</strong>を確立するサービスです。
インターネット経由で暗号化されたトラフィックを送受信し、リモートユーザーや拠点間ネットワークを安全にAzureへ接続できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">サイト間（S2S）VPN：</span>オンプレミスのVPNデバイスとAzure間で永続的なIPsecトンネルを確立します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ポイント対サイト（P2S）VPN：</span>個々のクライアントPCから直接AzureへセキュアなVPN接続を確立します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">VNet間（VNet-to-VNet）VPN：</span>異なるリージョン・サブスクリプションのVNet同士を接続します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">BGP対応：</span>動的ルーティングプロトコルにより複数経路の自動フェイルオーバーを実現します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. 接続タイプ</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">タイプ</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Site-to-Site (S2S)</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">オンプレミスのオフィス・データセンターとAzureを恒久的に接続</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Point-to-Site (P2S)</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">リモートワーカーの個人端末からAzureへ安全に接続</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>VNet-to-VNet</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">異なるAzureリージョン・サブスクリプション間のVNetを接続</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>マルチサイト</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">単一のVPN Gatewayで複数拠点と同時接続</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. SKU（ゲートウェイサイズ）</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">SKU系統</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Basic</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">小規模検証向け。一部の高度な機能（BGP等）は非対応</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>VpnGw1〜5</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">標準的な本番ワークロード向け。トンネル数・スループットに応じた段階的なサイズ</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>VpnGw1AZ〜5AZ</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">可用性ゾーン対応版。ゾーン障害への耐性を強化</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">アクティブ-アクティブ構成：</span>2つのゲートウェイインスタンスを同時稼働させ可用性とスループットを向上させます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ExpressRoute共存：</span>同一VNetでVPN GatewayとExpressRouteを併用しフェイルオーバー経路を構築できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">複数認証方式：</span>P2S接続でMicrosoft Entra ID認証・証明書認証・RADIUS認証から選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">カスタムIPsec/IKEポリシー：</span>暗号化アルゴリズム・整合性アルゴリズムを要件に応じて指定できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ゲートウェイ稼働時間：</strong>選択したSKU（Basic〜VpnGw5AZ）に応じた時間単位の固定料金が発生します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>P2S接続：</strong>同時接続ユーザー数が一定数を超えると追加課金が発生する場合があります。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>データ転送：</strong>VNet間接続やアウトバウンドデータ転送には標準のデータ転送料金が適用されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/vpn-gateway/
https://azure.microsoft.com/ja-jp/pricing/details/vpn-gateway/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure VPN Gatewayは<strong>オンプレミスとAzureを安全に接続するIPsec VPNサービス</strong>です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>S2S・P2S・VNet-to-VNet</strong>の3種類の接続タイプで多様なネットワーク要件に対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>用途に応じて<strong>Basic〜VpnGw5AZまで複数のSKU</strong>から選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ExpressRouteとの共存</strong>により高可用性なハイブリッド接続を実現できます。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
