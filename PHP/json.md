### jsonファイル作成方法
```
$json_sample = [
    'title' => 'JSONサンプル',
    'items' => [
        'items01' => '1つめ',
        'items02' => '2つめ'
     ]
];

$file = json_encode($json_sample, JSON_UNESCAPE_UNICODE); //'JSON_UNESCAPE_UNICODE'は、ユニコードにエスケープしないという定義済み定数
file_put_contents('./json_sample.json', $file);
```

### Decode / Encodeとは？
Decode : コードを復元する。（Encodeされたコードを復元）  
Encode : データを違う形式に変換する。
