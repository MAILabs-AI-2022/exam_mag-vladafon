![Open in Codespaces](https://classroom.github.com/assets/open-in-codespaces-abfff4d4e15f9e1bd8274d9a39a0befe03a0632bb0f153d0ec72ff541cedbe34.svg)
# Классификация языков

В файлах [dutch.txt](dutch.txt), [hungarian.txt](hungarian.txt) и [portugese.txt](portugese.txt) содержатся словари самых часто употребляемых слов Датского, Венгерского и Португальского языков соответственно. Ваша задача - построить нейросетевой классификатор для определения языка.

Результаты сохраняйте в файле [LangDetector](LangDetector.ipynb). Разбейте датасет на обучающую и проверочную выборку в пропорциях 80:20, посмотрите на точность в процессе обучения модели. 

> Если вы не можете целиком выполнить задание - начните с описания архитектуры нейросети и предполагаемого подхода к решению. Можете писать свои соображения прямо в этом файле.

________________________________

Модель здесь будет использоваться one-to-one (на каждое слово выдается класс). Задача многоклассовой классификации (3 класса). На выходе softmax, loss - categroical_crossenthropy. 

Сама модель по структуре - обычная нейросеть.

Основная задача здесь - предобработка входных данных. Слова из файлов были записаны в dataframe с указанием класса (класс закодирован one-hot-encoding). Далее были удалены бесполезные слова, знаки препинания, цифры. Далее все собиралось в один датасет, над которым была произведена векторизация.

Каждое слово было представлено набором букв, из которых оно состоит. На основе датасета был получен словарь уникальных букв. Каждое слово преобразовалось в вектор длиной такой же, как и словарь. Каждое значение внутри вектора - количество повторений данной буквы в слове.

После подготовки входных данных, было произведено обучение на сети (1 вх, 1 вых, 2 скрытых слоя).


