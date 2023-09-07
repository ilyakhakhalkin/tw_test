### step 2
*Создать три вложенных каталога: A/B/D*
```
mkdir A && cd A
mkdir B && cd B
mkdir D && cd D
```
### step 3
*В каталоге «D» создать файл «dummy» и заполнить его dummy-данными с помощью Vim или nano*
```
nano dummy
echo 'dummy data' >dummy (или заполнить вручную)
```
## step 4
*1. используя команду cat записать содержимое файла «dummy» в каталоге «D» в файл «dummy_2» в каталоге «B»*
```
cd ..
cat D/dummy > dummy_2
```
### step 5
*Удалить файл «dummy»*
```
rm D/dummy
```
### step 6
*Переименовать файл «dummy_2» в «dummy»*
```
mv dummy_2 dummy
```
### step 7
*Скопировать файл «dummy» в каталог «D»*
```
cp dummy D
```
### step 8
*Перенести файл «dummy» из каталога «B» в каталог «A»*
```
mv dummy ..
```
### step 9
*Создать в каталоге «A» файл с именем «[date]», где [date] — текущие дата и время системы*
```
cd ..
touch $(date +"%Y-%m-%d")
```

### step 10
*Записать в этот файл расположение исполняемого файла, справочных страниц, исходного кода и т.д. "nano"*
```
whereis nano >> 2023-09-07
```

### step 11
*Вывести дерево каталога «A» со всеми вложениями*
```
cd ..
ls -R
```

или
```
cd ..
sudo apt install tree
tree
```

### step 12
*Написать bash скрипт для загрузки, разархивирования и переименнования файла по ссылке https://www.sqlitetutorial.net/wp-content/uploads/2018/03/chinook.zip*
```
nano downloader.sh
```

Скрипт:
```
#!/bin/bash

mkdir -p downloaded

curl -L -o downloaded/chinook.zip https://www.sqlitetutorial.net/wp-content/uploads/201$

cd downloaded
unzip chinook.zip
mv chinook.zip renamed.zip
```