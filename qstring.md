
# QString


> QString QString::arg ( int a, int fieldWidth = 0, int base = 10, const QChar & fillChar = QLatin1Char( ' ' ) ) const

格式化 int 為 QString
```
int d = 12;
QString s = QString("%1", d, 4, 10, QChar('0'));  
// 字串寬度為 4, 數字 10 進位表示, 多餘的空間補 0, 結果：0012
```
