<div style="font-size:32px; color:#000000; text-align: center;font-weight:bold;">Azure Blob Storage</div>
<div style="font-size:24px; color:#000000; text-align: center;font-weight:bold;">(Microsoft Azure Blob Storage) 入門</div>
<hr style="height:3px; background-color:#0078D4; border:none;">
<div style="background-color:#E5F1FB; padding:0px; border:2px solid #C7E0F4;">
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">【コンテンツに関する注意事項】</p>
  <p style="color:#000000; font-size:12px; margin:10px 0; padding-left:10px;">・本資料は2026年時点のサービス内容および料金を解説しています。<br>・最新情報はMicrosoft Azure公式ウェブサイトをご確認ください。<br>・本資料の料金と公式サイトに差異がある場合は、公式サイトの料金が優先されます。<br><a href="https://learn.microsoft.com/en-us/azure/storage/blobs/" target="_blank" style="color:#0078D4;font-size:15px; padding-left:12px;">https://learn.microsoft.com/en-us/azure/storage/blobs/</a></p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:50px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">前提知識</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>オブジェクトストレージの基本概念</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure ストレージアカウントの基本知識</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>アクセス制御の基礎知識（SAS・Microsoft Entra ID）</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:0px 10; padding-left:10px;">対象者</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>非構造化データの保存・配信基盤を構築するアプリケーション/データエンジニア</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Blob Storageの基礎を理解したい方</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>静的Webサイトホスティングやバックアップ基盤を検討する方</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">アジェンダ</p></div>
<div style="background-color:#FAFAFA; padding:0px; border:1px solid #C7E0F4; border-radius:8px;">
  <p style="color:#333333; font-size:18px; margin:30px 0; padding-left:30px;">1. Azure Blob Storageとは？<br>2. Blobの種類とアクセス層<br>3. データ冗長性オプション<br>4. 主要機能<br>5. 料金<br>6. まとめ</p>
</div>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">1. Azure Blob Storageとは？</p></div>

テキスト・バイナリデータなど大量の非構造化データを保存するための<strong>高い拡張性とコスト効率を持つオブジェクトストレージサービス</strong>です。
画像・動画・ログファイル・バックアップデータなど多様なデータを、容量無制限かつ高耐久性で保存できます。

<h4 style="color:#0078D4; border-bottom:3px solid #E5F1FB; padding-bottom:6px;">主要機能</h4>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">階層型アクセスレベル：</span>Hot・Cool・Cold・Archiveの4階層でアクセス頻度に応じたコスト最適化が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">高耐久性：</span>冗長化オプションにより最大99.999999999%（11ナイン）の年間データ耐久性を実現します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">ライフサイクル管理：</span>ルールベースで古いデータを自動的に低コストの階層へ移行または削除できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">REST API/SDK：</span>HTTPS経由でどこからでもアクセス可能。各種言語向けSDKが提供されています。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">2. Blobの種類とアクセス層</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">種類/階層</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ブロックBlob</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">テキスト・バイナリデータ向けの最も一般的な形式。大容量ファイルをブロック単位で分割管理</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>追加Blob（Append Blob）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ログデータなど末尾への追記に最適化</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ページBlob</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">VHDファイルなどランダムアクセス読み書きに対応（VMディスクの基盤）</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>Hot / Cool / Cold / Archive層</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">アクセス頻度順にストレージ単価は下がるが取得コストと取得時間は増加</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">3. データ冗長性オプション</p></div>
<table style="border-collapse:collapse; width:100%; margin-top:20px;">
  <thead>
    <tr style="background-color:#0078D4; color:#FFFFFF;">
      <th style="border:1px solid #C7E0F4; padding:8px;">冗長性</th>
      <th style="border:1px solid #C7E0F4; padding:8px;">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>LRS（ローカル冗長）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">単一データセンター内で3つのコピーを保持。最も低コスト</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>ZRS（ゾーン冗長）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">同一リージョン内の複数可用性ゾーンに複製</td></tr>
    <tr style="background-color:#F3F2F1;"><td style="border:1px solid #C7E0F4; padding:8px;"><strong>GRS（geo冗長）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ペアとなる別リージョンに非同期複製。リージョン障害に対応</td></tr>
    <tr><td style="border:1px solid #C7E0F4; padding:8px;"><strong>GZRS（geoゾーン冗長）</strong></td><td style="border:1px solid #C7E0F4; padding:8px;">ZRSとGRSを組み合わせた最高水準の可用性・耐久性</td></tr>
  </tbody>
</table>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">4. 主要機能</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">静的Webサイトホスティング：</span>HTML/CSS/JSをBlob Storageから直接配信し、CDNと組み合わせて低コストなWebサイトを構築できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">Azure Data Lake Storage Gen2：</span>階層型名前空間を有効化することでビッグデータ分析基盤としても活用できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">不変ストレージ（Immutable Storage）：</span>WORM（Write Once Read Many）ポリシーでコンプライアンス要件に対応します。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><span style="font-weight:bold;">イベントグリッド連携：</span>Blobのアップロード・削除イベントをトリガーにAzure Functionsなどを自動実行できます。</li>
</ul>
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10; padding-left:10px;">5. 料金</p></div>
<ul style="list-style:none; padding-left:0;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ストレージ容量：</strong>保存データ量（GB単位）に対して階層・冗長性オプションごとの単価で課金されます。Hot層が最も高単価、Archive層が最も低単価です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>操作コスト：</strong>読み取り/書き込みなどのトランザクション数にも課金が発生し、階層が低いほど操作単価は高くなります。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>データ取得・早期削除コスト：</strong>Cool/Cold/Archive層からのデータ取得には別途料金が発生し、一定期間内の削除には早期削除料金がかかります。</li>
</ul>

<div style="height:20px;"></div> 参考リンク

https://learn.microsoft.com/en-us/azure/storage/blobs/
https://azure.microsoft.com/ja-jp/pricing/details/storage/blobs/
<div style="background-color:#FFFFFF; padding:10px;"><p style="margin:10px 0;"></p></div>
<div style="background-color:#F3F2F1; padding:0px; border-left:6px solid #0078D4;"><p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">まとめ</p></div>
<ul style="list-style:none; padding-left:0; margin-top:10px;">
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>Azure Blob Storageは<strong>大規模非構造化データ向けのオブジェクトストレージ</strong>。高い耐久性とスケーラビリティが特長です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>Hot/Cool/Cold/Archive</strong>の4階層によりアクセス頻度に応じたコスト最適化が可能です。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span><strong>ライフサイクル管理ポリシー</strong>でデータの階層移行・削除を自動化できます。</li>
  <li style="margin-bottom:8px;"><span style="color:#0078D4; margin:0 6px 0 10px;">▶</span>静的Webサイトホスティングからビッグデータ分析（Data Lake）まで<strong>幅広い用途</strong>に対応します。</li>
</ul>
<div style="background-color:#F3F2F1; padding:0px; text-align:left; border-left:6px solid #0078D4;">
  <p style="color:#000000; font-size:25px; font-weight:bold; margin:40px 10px; padding-left:10px;">本資料に関するお問い合わせ・フィードバック</p>
</div>

- Microsoft Azureに関する技術的なお問い合わせは、Microsoft公式サポートポータルをご利用ください：
https://azure.microsoft.com/ja-jp/support/options/
- 請求に関するお問い合わせは、Azure請求サポートにお問い合わせください（Azure Portalへのログインが必要）：
https://portal.azure.com/
