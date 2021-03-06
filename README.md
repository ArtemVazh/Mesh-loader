Разработать конечно-элементный загрузчик сеток.

1. Предусмотреть возможность работы с различными форматами файлов КЭ-сетки. Создать базовый класс MeshLoader. Объявить в нем чисто виртуальный метод LoadMesh.

2. Создать производный от MeshLoader класс AneuMeshLoader, в котором переопределить метод LoadMesh. Данный класс должен обеспечивать загрузку сетки из формата .aneu.

3. Предусмотреть возможность консольного запуска бинарного файла и передачи имени загружаемого файла в параметрах командной строки.

4. В отдельном h-файле создать следующие вспомогательные типы данных:

* Node – тип данных «узел». Хранит ID узла (>= 1), декартовы координаты узла и флаг, определяющий, является ли данный узел вершиной КЭ или его внутренним узлом.

* Element – тип данных «конечный элемент». Хранит ID КЭ (>= 1), ID типа материала, к которому принадлежит КЭ по данным файла сетки, список ID узлов КЭ.

* Surface – тип данных «поверхностный конечный элемент». Хранит ID поверхностного элемента (>= 1), ID типа КЭ, ID поверхности с данным типом граничного условия, список ID узлов поверхностно КЭ.

5. Предоставить следующие методы:

* методы, позволяющие получить STL-контейнеры узлов, конечных элементов и поверхностных элементов1;

* метод, позволяющий найти КЭ по ID трех его вершинных узлов, для чего использовать алгоритм find_if и создать необходимый предикат. Предусмотреть возможность наличия нескольких КЭ с данными тремя узлами;

* метод, позволяющий найти КЭ по ребру, заданному с помощью ID двух узлов. Предусмотреть возможность наличия нескольких КЭ с данным ребром;

* метод, возвращающий контейнер поверхностных узлов по ID поверхности;

* метод, возвращающий контейнер КЭ с заданным ID материала;

* метод, возвращающий контейнер поверхностных КЭ с заданным ID поверхности;

* метод, преобразующий симплексные тетраэдральные КЭ в квадратичные путем внесения новых узлов в загруженную КЭ сетку. Новые узлы должны располагаться в середине ребер существующих КЭ;

* метод, создающий контейнер, n-ый элемент которого хранит контейнер всех «соседей» для узла n;

* методы, реализующие отформатированный вывод Node, Element и Surface в консоль;

* при необходимости возможно определение других методов и типов данных.
