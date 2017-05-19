# AndroidStudio2.3 AttensionPoints

## 処理の流れ
- アプリの最初は`onCreate`メソッドから始まります

- `setContentView(R.layout.activity_main);`の`activity_main`の部分には、このソースに対応したxmlファイルの名前を記述します。

- `EditText`や`TextView`等のコンポーネントは、`findViewById(R.id.button)`でフィールドに代入してIDを保存する等しておきます。

- ボタンは`fineViewById(R.id.button).setOnClickListener(this);`でボタンのリスナークラスを登録します。`button`と書かれているところは自分の設定したボタンの名前に置き換えてください。

- `EditText`で入力をキーとして動作をさせたい時は、テキストが変更される前、変更されるとき、テキストが変更された後の3段階で呼ばれるメソッドに処理を書くことができます。(全てTextWatcherのOverride)
	- `public void beforeTextChanged(CharSequence s, int start, int count, int after){}`
	- `public void onTextChanged(CharSequence s, int start, int before, int count){}`
	- `public void afterTextChanged(Editable s){}`

- ボタンをクリックしたときの処理は`public void onClick(View v){}`記述します。`v.getId();`でint型のIDを取得します。そのIDをR.id.buttonと等価することによって、どのボタンが押されたか判定できる。

- 画面遷移する場合は1つの画面ごとに、Activityクラスを分けるべきです。`Intent intent = new Intent(this, AnotherActivity.class);`で遷移先で使うActivityクラスを設定します。そして遷移先から戻り値が必要な場合は`startActivityForResult(intent, 1);`を、必要ない場合は`startActivity(intent, 1);`を実行します。`1`の部分は複数画面で構成されている場合に、任意のCodeを渡すことによって帰って来た時にどの画面かCodeで判別することができます。(Codeはフィールドのfinalで宣言しておくと便利です)

- 画面遷移先から遷移もとに戻るときには複数の戻り方があります。 戻り値ありの遷移だった場合、`Intent data = new Intent();`でデータの入れ物を作成。`data.putExtra("result", result);`でkeyとvalueを設定。`setResult(RESULT_OK, date);`で戻り値が正常であることと、データを格納したIntentをセットします。戻り値が取得できなかった場合、`RESULT_CANCELED`をセットします。
