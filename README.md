# Cheat programs for Minesweeper and Doom.

## О чём речь
Это проект DevDays Spring 2017. Мы занимались написанием программ, дающих преимущество в старых играх. В качестве самой простой игры выбрали Minesweeper - а именно, одну из версий, написанную на С++ и найденную на GitHub. 

Участники:
- Кольцов Михаил
- Кравцун Андрей
- Тищенко Олеся


## Как собрать

### Сапёр
Требования (тестировали всё под этими установками):
- Windows 10
- Miscrosoft Visual Studio 2015
- QtCreator 5.6
Для начала, нужно собрать Minesweeper. Мы это делали с помощью QtCreator с компилятором MSVS 2015. Для этого в файле Minesweeper/src/minesweeper.pro нужно удалить строчки:
```
QMAKE_CXX=clang++
QMAKE_CXXFLAGS += --std=c++11
```
Потом нужно скомпилировать `find_mines_prototype.cpp` - для этого мы создавали проект типа "консольное приложение с++" в Visual Studio.

Чтобы увидеть действия чит-программы, нужно выполнить следующее:
1. Запустить Minesweeper.exe (скомпилированный на начальном шаге). Убедитесь, что название файла именно такое! Возможно, потребуется использовать команду `PATH_TO_QT/5.6/bin/windeployqt.exe PATH_TO_SWEEPER_EXE`, чтобы Qt положил все нужные .dll-файлы к exe-шнику;
2. Запустить нашу программу. Она автоматически определяет запущенный Minesweeper и подключается к нему;
3. Кликнуть хотя бы на одно поле в игре (до этого момента мины не инициализируются, поэтому их не существует). Наша программа просканирует память процесса Minesweeper.exe, найдёт там все мины, пометит их, переключит с помощью alt+tab окно (чтобы GUI сапёра обновился) - и вы увидите флажки на тех и только тех местах, где есть мины:
![result](https://cloud.githubusercontent.com/assets/6823298/25706775/17e796c0-30ea-11e7-8e83-f3f8115500b3.PNG)


### Doom
TODO
