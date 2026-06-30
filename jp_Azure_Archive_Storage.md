<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Archive Storage</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Azure Blob Storage Archive Tier) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Blob Storageの基本概念とアクセス層</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>長期データ保存・コンプライアンス要件の基礎知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>ライフサイクル管理ポリシーの基本知識</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>長期バックアップ・コンプライアンスデータを低コストで保存したいデータ管理者</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Archive Storageの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>テープバックアップ等のレガシーアーカイブ基盤を置き換えたい方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Archive Storageとは？<br>2. アクセス層比較<br>3. データの取得（リハイドレート）<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Archive Storageとは？</p></div>

Azure Blob Storageの最も低コストなアクセス層として提供される<strong>長期データ保持向けのストレージティア</strong>です。
データはオフラインで保存されるため即座のアクセスはできませんが、最も低いストレージ単価で大量の非アクティブデータを長期保存できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">最低水準のストレージ単価：</span>Hot/Cool/Cold層と比較して最も低いGBあたりの保存コストを実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">柔軟なリハイドレート：</span>標準/高優先度の2つの優先度レベルでデータをオンライン層に復元できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ライフサイクル管理連携：</span>ルールに基づきHot/Cool層から自動的にArchive層へ移行できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">不変ストレージ対応：</span>WORMポリシーと組み合わせて規制対応の長期保存要件を満たせます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. アクセス層比較</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">層</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">アクセス可否</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">推奨用途</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Hot</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">即時オンラインアクセス</td><td style="border:1px solid #C7E0F4; padding:8px;">頻繁にアクセスされるデータ</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Cool</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">即時オンラインアクセス</td><td style="border:1px solid #C7E0F4; padding:8px;">30日以上アクセスされないデータ</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Cold</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">即時オンラインアクセス</td><td style="border:1px solid #C7E0F4; padding:8px;">90日以上アクセスされないデータ</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Archive</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">オフライン（要リハイドレート）</td><td style="border:1px solid #C7E0F4; padding:8px;">180日以上アクセス不要な長期保存データ</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. データの取得（リハイドレート）</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">優先度</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">所要時間の目安</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>標準（Standard）優先度</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">15時間以内（多くは数時間程度）</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>高（High）優先度</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">1時間未満（小サイズBlobの場合、追加料金あり）</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ライフサイクル管理ポリシー：</span>最終アクセス日や作成日からの経過日数に基づき、Hot→Cool→Cold→Archiveへ自動移行するルールを定義できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">最低保存期間：</span>Archive層には180日間の最低保存期間が設定されており、それ以前の削除/階層変更には早期削除料金が発生します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Blobレベルでの階層管理：</span>コンテナ単位ではなく個々のBlob単位でArchive層を指定できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">監査・コンプライアンス対応：</span>法規制が求める長期保存要件（金融・医療記録等）に低コストで対応できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ストレージ容量：</strong>Hot/Cool/Cold層と比較して最も低いGBあたりの保存料金です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>データ取得（リハイドレート）コスト：</strong>取得するデータ量と優先度（標準/高）に応じて課金されます。高優先度の方が単価は高くなります。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>早期削除料金：</strong>180日の最低保存期間内に削除・階層変更すると残存期間分の料金が請求されます。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview/
https://azure.microsoft.com/ja-jp/pricing/details/storage/blobs/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Archive Storageは<strong>最も低コストな長期データ保存層</strong>。オフライン保存により大幅なコスト削減を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>データ取得には<strong>リハイドレート処理</strong>が必要で、優先度により所要時間とコストが異なります。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ライフサイクル管理ポリシー</strong>でHot/Cool/ColdからArchiveへの自動移行を設定できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>180日の最低保存期間</strong>があるため、早期削除コストを考慮した設計が重要です。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
