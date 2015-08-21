# Практика 5. Оптимизация производительности

[![Build Status](https://travis-ci.org/Itseez-NNSU-SummerSchool2015/practice5-performance.svg)](https://travis-ci.org/Itseez-NNSU-SummerSchool2015/practice5-performance)

## Цели

__Цель данной работы__ - получить представление о задаче оптимизации производительности программного кода.

## Общая структура репозитория

Данный репозиторий содержит:

  - `include`, `src` -- директории содержащие реализацию фильтра "старое кино".
  - `testdata` -- директория с тестовыми видео и масками необходимыми для работы фильтра.
  - `sample` -- директория с С++-приложением, осуществляющим обработку видео,
     производительность которого необходимо улучшить.
  - `.gitignore` -- список файлов, находящихся в директории проекта,
     но игнорируемые git'ом.
  - `.travis.yml` -- конфигурационный файл для системы автоматического
     тестирования Travis-CI.
  - `CMakeLists.txt` -- общий файл для сборки проекта с помощью CMake.
  - `README.md` -- информация о проекте, которую вы сейчас читаете.

## Задачи

__Основные задачи:__

  1. Оценить производительность приложения.
  1. Проанализировать код, найти узкие места (bottlenecks).
  1. Добиться более высокой производительности, не изменяя результат работы
     приложения.
  1. Добавить режим видео конвертера - входной видео файл преобразуется в
     выходной, без визуализации.
  1. Добиться максимальной скорости преобразования видео в новом режиме.

__Дополнительные задачи:__

  1. Реализовать фильтр "старое кино" без использования функций библиотеки
     OpenCV (кроме необходимых для доступа к элементам изображения).

## Общая последовательность действий

  1. Сделать форк upstream-репозитория, затем клонировать origin к себе на
     локальную машину. Для инструкций можно обратиться к разделу
     [Общие инструкции по работе с Git][git-intro]
     в [практической работе 1][practice1].
  1. Собрать проект с помощью CMake и MS VS (см. раздел
     [Сборка проекта с помощью CMake и MS VS][cmake-msvs]
     в [практической работе 1][practice1]). В результате успешной сборки
     в build-каталоге в директории `bin` должен появиться исполняемый файл
     `retro_sample.exe`
  1. Запустить приложение используя видео камеру:

      `./bin/retro_sample.exe --border testdata/fuzzy_border.png --scratches testdata/scratches.png --camera`

      или тестовое видео

      `./bin/retro_sample.exe --border testdata/fuzzy_border.png --scratches testdata/scratches.png --video testdata/05.avi`
  1. Решить задачи из списков [основных и дополнительных задач][tasks].

<!-- LINKS -->

[practice1]: https://github.com/Itseez-NNSU-SummerSchool2015/practice1-devtools
[git-intro]: https://github.com/Itseez-NNSU-SummerSchool2015/practice1-devtools#Общие-инструкции-по-работе-с-git
[cmake-msvs]: https://github.com/Itseez-NNSU-SummerSchool2015/practice1-devtools#Сборка-проекта-с-помощью-cmake-и-microsoft-visual-studio
[tasks]: https://github.com/Itseez-NNSU-SummerSchool2015/practice5-detection#Задачи
