# Российский университет дружбы народов
### факультет физико-математических и естественых наук






## Отчет по лабараторной рабете № 15
### *дисциплина : Операционыые системы*
*студент Блохин александр НКН*

**Москва**

***2021***

## Цель работы

Приобретение практических навыков работы с именованными каналами.

## **Ход работы**
Изучите приведённые в тексте программы server.c и client.c. Взяв данные
примеры за образец, напишите аналогичные программы, внеся следующие изменения:
1. Работает не 1 клиент, а несколько (например, два).
2. Клиенты передают текущее время с некоторой периодичностью (например, раз
в пять секунд). Используйте функцию sleep() для приостановки работы клиента.
3. Сервер работает не бесконечно, а прекращает работу через некоторое время (например, 30 сек). Используйте функцию clock() для определения времени работы
сервера. Что будет в случае, если сервер завершит работу, не закрыв канал


![clipboard](https://i.imgur.com/mkoofpt.png)

![clipboard](https://i.imgur.com/MFBZkho.png)

![clipboard](https://i.imgur.com/GdVUxp4.png)

![clipboard](https://i.imgur.com/SnkKyGG.png)

![clipboard](https://i.imgur.com/d67V2hk.png)

![clipboard](https://i.imgur.com/YfXsNfF.png)

![clipboard](https://i.imgur.com/ir3LA3x.png)

![clipboard](https://i.imgur.com/IMm7ZJg.png)

## Вывод
Приобрел практическиие навыки работы с именованными каналами.

## контрольные вопросы

1. Именованные каналы отличаются от неименованных наличием идентификатора канала, который представлен как специальный файл (соответственно имя именованного канала — это имя файла). Поскольку файл находится на локальной файловой системе, данное IPC используется внутри одной системы
2. Для создания неименованного канала используется системный вызов pipe. Массив из двух целых чисел является выходным параметром этого системного вызова.
3. Вызов функции mkfifo() создаёт файл канала
4. 4 int read(int pipe_fd, void *area, int cnt);
Int write(int pipe_fd, void *area, int cnt);
Первый аргумент этих вызовов - дескриптор канала, второй - указатель на область памяти, с которой происходит обмен, третий - количество байт. Оба вызова возвращают число переданных байт (или -1 - при ошибке).
5. int mkfifo (const char *pathname, mode_t mode); Первый параметр — имя файла, идентифицирующего канал, второй параметр маска прав доступа к файлу. Вызов функции mkfifo() создаёт файл канала (с именем, заданным макросом FIFO_NAME): mkfifo(FIFO_NAME, 0600);
6. При чтении меньшего числа байтов, чем находится в канале или FIFO, возвращается требуемое число байтов, остаток сохраняется для последующих чтений.
7. При чтении большего числа байтов, чем находится в канале или FIFO, возвращается доступное число байтов. Процесс, читающий из канала, должен соответствующим образом обработать ситуацию, когда прочитано меньше, чем заказано.
8. да
9. Функция write() переписывает count байт из буфера, на который указывает bufy в файл, соответствующий дескриптору файла handle. Указателю положения в файле дается приращение на количество записанных байт.
10. Строковая функция strerror - функция языков C/C++, транслирующая код ошибки, который обычно хранится в глобальной переменной errno, в сообщение об ошибке, понятном человеку.