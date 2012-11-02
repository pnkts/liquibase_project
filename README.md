# liquibase_project
## Install
antが必要
<https://www.google.co.jp/search?q=ant+install>
## How to
### 既にあるデータベースからchangelog作成
    $ant db:generateChangeLog
    input config type >sample
    チェンジログの名前 >first
    $ant db:changeLogSync
### changelog作成
    $ant db:makeChangeLogFile
    チェンジログの名前 >test
### データベースのdiffからchangelog作成
    $ant db:diffChangeLog
    チェンジログの名前 >diff
    比較元のURL >locahost:8889
    比較元のデータベース名前 >diff_db_name
    比較元のユーザ >root
    比較元のPassword >root
### changelogよりデータベース更新
    $ant db:update
### 設定変更
    $cat dbconfig/develop.properties
    #liquibase.properties
    driver: com.mysql.jdbc.Driver
    url:jdbc:mysql://localhost:8889/develop_db_name
    username: root
    password: root
    $ant db:changePropertiesFile
    input config type >develop
### Document作成
    $ant db:generateDocument