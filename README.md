# modeller-test-matlab
Моделирование КС (общее)
Тестовое задание для выполнения в MATLAB или совместимых средах.,

Требования к выполнению
- Ответы на вопросы тестового задания должны получаться без дополнительных манипуляций с кодом, т.е. вызовом отдельного скрипта / функции, проверяющему должно быть очевидно, что нужно сделать для проверки выполнения. Допускается для этого написать отдельную инструкцию, описывающую процесс вызова решения;
- Написание текстового отчета по алгоритму решения не требуется. Хороший код документирует сам себя - крайне рекомендеются использовать понятные названия переменных и комментарии, поясняющие основные шаги при решении (документ с требованиями и рекомендациями, приложенный к заданию, в точности соблюдать не требуется, но он может помочь для структуризации и улучшения качества кода);
- Ожидаемая форма предоставления результата - pull request в исходный репозиторий; при отсутствии достаточного опыта работы с git - допускаются другие, удобные для исполнителя формы.

Содержание репозитория
Для выполнения задания нами предоставляется исходный код в составе:
- constellationTest.json – конфигурационный файл с данными для инициализации орбитальной конфигурации космической системы
- gatewaysTest.json – файл с координатами расположения шлюзовых станций
- Constellation.m – файл, реализующий класс Constellation (орбитальная группировка), 
- example.m – пример работы с объектом типа Constellation

Для справки
При вычислении зон обзора поверхности Земли космическим аппаратом (КА) используются следующие параметры и обозначения (рис. 1):
a – угол обзора (половина угла раствора конуса с вершиной в точке S и центральной осью, проходящей через центр Земли),
ε – угол места.

![alt text](./coverage.png "Рис. 1 - базовые геометрические параметры покрытия")

Во всех задания ниже поверхность Земли считается идеальной сферой с неподвижным центром. Ось вращения Земли совпадает с осью z принятой инерциальной системы координат с началом в центре Земли. Нулевой меридиан на начальную эпоху принадлежит плоскости xz неподвижной системы координат.

Орбитальная конфигурация системы состоит из двух групп спутников (каждая группа имеет свою высоту орбиты). Внутри каждой группы КА принадлежат к нескольким орбитальным плоскостям. Плоскости равномерно распределены по долготе, а КА равномерно распределены по окружностям орбит в каждой из плоскостей.

Задание:

	Code review – предложите правки по логике и оформлению предоставленного вам кода (StyleGuide прилагается)

	Реализуйте вычислительную процедуру, проверяющую, обеспечивает ли выбранная орбитальная конфигурация глобальное покрытие поверхности Земли в зависимости от значения угла a (ограничения на угол места отсутствуют).
    Примените реализованную процедуру для орбитальной конфигурации, соответствующей constellationTest.json в начальный момент времени. Найдите минимальное значение a, при котором глобальное покрытие обеспечивается (точность – 3 градуса).

	В файле gatewaysTest заданы координаты шлюзовых станций, расположенных на Земле. Реализуйте вычислительную процедуру, позволяющую для набора произвольных моментов времени определить, какие КА находятся в зоне видимости шлюзовых станций. Условие нахождения КА в зоне видимости шлюзовой станции – угол места ε ≥ 25° (ограничения на a не накладываются).

	Предположим, что КА системы оснащены межспутниковой линией связи (МЛС), которая устроена так, что информация может передаваться от КА к другим КА в его орбитальной плоскости. Воспользовавшись результатом предыдущего задания и предположив a=40°, определите наличие на поверхности Земли зон, не связанных спутниковой сетью (то есть существование точек на поверхности Земли, которые не могут быть обслужены КА, имеющими возможность пересылать информацию на шлюзовые станции).
