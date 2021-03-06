======================
レプリケーションの設定
======================

レプリケーションの設定
======================

|Fess| は指定されたパスにある Solr
のインデックスデータをコピーすることができます。クロールおよびインデックス作成用の
|Fess| と検索用 |Fess| の 2
台のサーバーを構築することで、インデックス作成時にかかる負荷を分散することができます。

|Fess| のレプリケーション機能を利用するためには Solr
のインデックスファイルを NFS などの共有ディスクにおいて、それぞれの |Fess| 
から参照できる必要があります。

構築方法
========

インデックス作成用 |Fess| の構築
------------------------------

|Fess| 
をダウンロードして、インストールします。\ ``/net/server1/usr/local/fess/``
にインストールしたとします。

|Fess| 
の起動後、通常の構築と同様にクロール設定を登録して、クロールしてインデックスを作成してください
(インデックス作成用 |Fess| の構築手順は通常の構築手順と特に変わりません)。

検索用 |Fess| の構築
------------------

|Fess| 
をダウンロードして、インストールします。\ ``/net/server2/usr/local/fess/``
にインストールしたとします。

|Fess| 
の起動後、管理画面のクロール全般の設定で「レプリケーション機能」のチェックボックスを有効にして、「スナップショットパス」を指定します。スナップショットパスは、インデックス作成用
|Fess| 
のインデックスの場所を指定します。今回の場合では、\ ``/net/server1/usr/local/fess//solr/core1/data/index``
になります。

|image0|

更新ボタンを押下してデータを保存すると、スケジュールで設定された時間でインデックスのレプリケーションが実行されます。

.. |image0| image:: ../../../resources/images/ja/4.0/crawl-2.png
