ファイルの先頭にアンダーラインを追加するだけ。

@echo off
setlocal enabledelayedexpansion

for %%F in (%*) do (
    set "filepath=%%~fF"
    set "folder=%%~dpF"
    set "filename=%%~nF"
    set "extension=%%~xF"

    rem 新しいファイル名を作成（先頭に "_" を追加）
    set "newname=_!filename!!extension!"

    rem ファイルをリネーム
    ren "!filepath!" "!newname!"
)

endlocal
exit
