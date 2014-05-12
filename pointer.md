# Pointer & Reference

`*` 符號有兩個意思
* 在定義時代表這個變數為指標 e.g. `int *ip`
* 在 = 號左邊時，代表 dereference (提領) operator，取指標的值，產生左值

`&` 符號也是有兩個意思
* 在定義時代表這個變數為某個變數的 reference (參照、別名)，和 pointer 不同的地方為，reference 總是指向某個物件，在定義時就要給初值
e.g 
```
int pi = 3.14;
int &rpi = pi;
```
* 在 = 號右邊時，代表取址運算子，把變數的記憶體位置取出



