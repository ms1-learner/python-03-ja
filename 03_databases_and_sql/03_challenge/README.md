# チャレンジ3: 楽曲の再生時間に応じたバケット分類

このチャレンジでは、楽曲の再生時間に応じてバケットに分類します。

- 楽曲の再生時間にもとづいて分類する **`track_length_buckets`** 関数を実装します。
- 各バケットの幅は**1分** (Chinookデータベースでは楽曲の再生時間がミリ秒単位で保存されているため60,000ミリ秒) にします。
- たとえば、バケット**1**には、再生時間が**0**ミリ秒から**60000**ミリ秒までのすべての楽曲が入ります。
- この関数では、(**`max_duration_in_minutes`**, **`track_count`**) のようなタプルのリストを返すようにします。