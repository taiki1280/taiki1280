# 便利な linux command

## .md ファイルすべての行数を調べる

```zsh
wc -l *.md
```

## ディレクトリー配下のすべてのディレクトリに対して git コマンドを実行

```zsh
# main ブランチへ切り替える
ls | xargs -I{} git -C {} switch main
# git pull する
ls | xargs -I{} git -C {} pull
```

## 実行場所以下のディレクトリ・ファイル権限を変更

```zsh:change_mode.sh
#!/usr/bin/bash
# ディレクトリの場合
find . -type d -print | xargs chmod 755
echo 'ディレクトリ権限を変更しました。'
find . -type d -print | xargs
echo -e "\n"
# ファイルの場合
find . -type f -not -name "change_mode.sh" | xargs chmod 600
echo 'ファイル権限を変更しました。'
find . -type f -not -name "change_mode.sh" | xargs
```

