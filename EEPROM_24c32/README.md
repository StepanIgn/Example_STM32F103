Запись ведётся кратно 32-м байтам, и не больше 32-х байт за одну транзакцию.

Если нужно записать 20 байт, то нужно указать адрес кратно 32-м. Например, если указать адрес 0, то данные запишуться с 0 по 19 ячейку. 
Если указать адрес 15, то первые 16 байт запишутся в ячейки с 15 по 31, а оставшиеся 4 байта запишутся в ячейки с 0 по 3.

Если нужно записать больше 32-х байт, тогда указываем адрес кратно 32 (например 32, 64 и т.д.) и пихаем их в функцию Write_mem(), далее программа сама разделит вес пакет по 32 байта и будет прибавлять адрес.
Вобщем просто пишем...

```
char wstr[120] = {0,};
...
Write_mem(0, wstr, strlen(wstr)); // адрес либо 0, либо 32, либо 64, и т.д.
```
... и не паримся.

Читать можно откуда угодно, и по сколько нужно.
