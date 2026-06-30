<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Disk Storage</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Azure Managed Disks) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/virtual-machines/managed-disks-overview/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/virtual-machines/managed-disks-overview/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ブロックストレージの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Virtual Machinesの基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>IOPS・スループットなどストレージ性能指標の基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>VMのストレージ性能・コストを最適化したいインフラエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Disk Storage（Managed Disks）の基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>データベースなど高負荷ワークロード向けのディスク設計を検討する方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Disk Storageとは？<br>2. ディスクの種類<br>3. ディスクの分類（OS/データ/一時）<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Disk Storageとは？</p></div>

Azure Virtual Machines向けに<strong>永続的なブロックストレージ</strong>を提供するマネージドディスクサービスです。
ディスクの可用性管理（複数コピーの保持・自動配置）をAzureが自動化するため、ストレージアカウントの容量制限やスケーラビリティを意識せずにVMへ高性能なストレージを接続できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高い耐久性：</span>3つのレプリカを自動的に保持し、99.999%以上のディスク可用性を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">スナップショット/イメージ：</span>ポイントインタイムのバックアップを取得し、新規VM作成のテンプレートとしても利用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ディスク暗号化：</span>Azure Disk EncryptionやServer-Side Encryption（SSE）により保存データを標準で暗号化します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">オンラインリサイズ：</span>多くのディスクで稼働中のVMを停止せずに容量を拡張できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. ディスクの種類</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">種類</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">特徴・用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Ultra Disk</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">最高水準のIOPS・スループット・サブミリ秒のレイテンシ。SAP HANAなどミッションクリティカル用途</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Premium SSD v2</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">パフォーマンスと容量を個別に調整可能。高性能データベース向け</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Premium SSD</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">本番環境やパフォーマンス重視のワークロード向けの標準的な高性能ディスク</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Standard SSD</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">一貫した性能とコストバランスを求めるWebサーバー・軽量本番環境向け</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Standard HDD</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">バックアップ・アーカイブなどコスト重視・低頻度アクセス向け</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. ディスクの分類（OS/データ/一時）</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">分類</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>OSディスク</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">VMのOSイメージをホストする必須ディスク。デフォルト最大2TiB</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>データディスク</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">アプリケーションデータ用に追加可能なディスク。VMサイズに応じて複数アタッチ可能</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>一時ディスク（Temporary Disk）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">VMに無料で付属するローカルディスク。再起動等でデータが消失するため永続データ非対応</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">共有ディスク（Shared Disks）：</span>複数VM間で単一のディスクを共有し、クラスタリングソリューション（Windows Server Failover Cluster等）を構築できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ディスクバースト：</span>Premium SSDで一時的な負荷増加に対して短時間の性能ブーストを提供します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ゾーン冗長ストレージ（ZRS）：</span>可用性ゾーンをまたいだディスクの複製でゾーン障害に対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">インクリメンタルスナップショット：</span>前回からの差分のみを保存し、バックアップコストを削減します。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Premium/Standard SSD・HDD：</strong>事前定義されたディスクサイズ（GB）単位の月額固定料金で課金されます（実使用量に関わらず確保した容量分）。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Ultra Disk・Premium SSD v2：</strong>プロビジョニングした容量・IOPS・スループットをそれぞれ個別に従量課金。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>スナップショット：</strong>使用したストレージ容量に応じた課金（インクリメンタルスナップショットは差分のみ課金）。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/virtual-machines/managed-disks-overview/
https://azure.microsoft.com/ja-jp/pricing/details/managed-disks/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Disk Storageは<strong>VM向けの永続的なマネージドブロックストレージ</strong>。可用性管理をAzureに任せられます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>性能要件に応じて<strong>Ultra〜Standard HDDまで5種類</strong>のディスクから選択可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>共有ディスク</strong>により複数VM間でのクラスタリング構成も実現できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>スナップショット</strong>を活用したバックアップとVMテンプレート化が可能です。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
