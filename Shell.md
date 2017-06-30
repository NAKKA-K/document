# Shellの書き方

## shellを実行
	$ bash file.sh
	又は
	$ chmod 755 file.sh
	$ ./file.sh
	chmodの第1引数の755の部分はたくさんの種類のモードが存在する。
	実行ファイルとしての権限であれば755が使われることが多い。
	通常ファイルであれば644が多い。


## 変数
date="`date +%H`" #date変数に``で囲んだコマンドの戻りテキストを代入している。""で囲むことによって安全策を実施している。
if [ "$date" == 12 ]; then #""で囲むことによって、変数の中身が無くてもエラーにならない
  echo "${date}"
fi


## if
if [ A == A ] && [ B == B ]; then #2回のコールで実行される
  echo 'true'
elif [ A == A -a B == B ]; then #オプションとしてのANDなので、コールが一回
  echo 'true'
else
  echo 'false'
fi

