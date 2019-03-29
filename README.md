# Sonia


Примеры получившихся сэмплов: [Пример 1](https://drive.google.com/open?id=1Jcx3-BOKz3J5UWQK99JBJttyVSAyl5ej)]  [Пример 2](https://drive.google.com/open?id=1s_L5TCKoKTNfnPO25m6cOf2wAGBA80sR)]
Для генерации музыки потребуются следующие библиотеки для установки:

    torch       pretty_midi         fluidsynth
    numpy       progress
    optparse    midi2audio

Генерация производится запуском файла gen_fin.py со следующими параметрами:

    -с      Это либо руками написанные распределения для учета стиля
                                при генерации, либо путь к файлу 
                                в котором уже заданы они (лучший вариант)
                                примеры таковых в папке test_train
                                в ней нужно выбрать любой из файлов
                                или как пример '1,0,1,1,0,1,0,1,1,0,0,1;4'
    -b      batch size (по умолчанию стоит 6) колличество итоговых файлов
    -s      Путь к файлу с моделью  (называется она final_2.sess)
    -o      Путь к дериктории для генерации файлов
    -l      Длина файла (по умолчанию 1100, следовательно задавать необязательно)
    -f      Путь к файлу с soundfont (если его не выбрать, то не будет генерации в wav
                                                            будет только midi)

Пример такого запуска:

    python3 gen_fin.py -s final_2.sess -c ./test_train/beethoven.data -o ./gen_mus -b 8 -f font.sf2

train_f.py это файл с обучением модели для такие параметры:

    -s      Путь к файлу с моделью в который будете сохранять
    -d      Путь к обработанному датасету
    -b      Задать batch size (необязательно уже задан по дефолту)
    -w      Задать window size (необязательно уже задан по дефолту)

Для воспроизведения музыки настоятельно рекомендуется плеер timidity++, так как 
при конвертации midi в wav очень влияет этот soundfont.
По ссылке можно найти на диске датасет, модель (final_2.sess)
и soundfont (font.sf2).
https://drive.google.com/open?id=1TwJhkTkN6UmYd3v9ky0Dak8fqpbHyaXk
