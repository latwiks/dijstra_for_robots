# Библиотека для работы с графами

Этот код представляет собой класс для работы с графами, использующий библиотеки NetworkX и Matplotlib. Он позволяет создавать графы на основе координат вершин и связей между ними, вычислять расстояния между вершинами, находить кратчайший путь между двумя заданными вершинами с помощью алгоритма Дейкстры и отрисовывать графы с учетом кратчайшего пути.

## Установка

Для работы с этим кодом вам нужно установить Python 3 и следующие библиотеки:

- NetworkX: `pip install networkx`
- Matplotlib: `pip install matplotlib`

## Использование

Для использования этого кода вам нужно импортировать класс Graph из файла main.py:

```python
from main import Graph
```

Затем вам нужно создать объект класса Graph, передав ему координаты вершин и связи между ними в виде списков кортежей:

```python
coordinates = [
    (1, 1.5),
    (4, 1.5), (15, 1.5),
    (15, 6.5), (12, 6.5),
    (8, 6.5), (4, 6.5),
    (1, 6.5), (1, 16),
    (6, 16), (7, 13),
    (9, 13), (12, 14),
    (16, 14), (16, 18),
    (12, 18), (9, 18),
    (9, 19.5), (8, 19.5),
    (8, 22), (6, 20),
    (4, 20), (4, 22),
    (10, 22), (10, 24),
    (16, 24), (15, 24)
]

connections = {
    (1, 1.5): [(4, 1.5)],
    (4, 1.5): [(15, 1.5), (4, 6.5)],
    (15, 1.5): [(15, 6.5)],
    (15, 6.5): [(12, 6.5)],
    (12, 6.5): [(8, 6.5)],
    (8, 6.5): [(7, 13), (4, 6.5), (9, 13)],
    (7, 13): [(9, 13)],
    (9, 13): [(9, 18)],
    (9, 18): [(9, 19.5), (12, 18)],
    (9, 19.5): [(8, 19.5)],
    (8, 19.5): [(8, 22)],
    (8, 22): [(10, 22)],
    (10, 22): [(10, 24)],
    (10, 24): [(15, 24)],
    (12, 18): [(16, 18)],
    (16, 18): [(16, 24)],
    (16, 24): [(15, 24)],
    (7, 13): [(6, 16)],
    (6, 16): [(6, 20)],
    (6, 20): [(4, 20)],
    (4, 20): [(4, 22)],
    (4, 22): [(8, 22)],
    (4, 6.5): [(1, 6.5)],
    (1, 6.5): [(1, 16)],
    (1, 16): [(6, 16)],
    (12, 14): [(16, 14), (12, 18)],
    (16, 14): [(16, 18)],
}
```

Для нахождения кратчайшего пути между двумя вершинами, вам нужно вызвать метод dijkstra_algorithm, передав ему координаты начальной и конечной вершины. Этот метод вернет список координат, составляющих кратчайший путь, и выведет его длину и последовательность на экран.

```python
shortest_path = graph.dijkstra_algorithm((1, 1.5), (15, 24))
```

Для отрисовки графа с учетом кратчайшего пути, вам нужно вызвать метод draw_graph, передав ему список координат кратчайшего пути. Этот метод создаст графическое окно, в котором вы увидите граф с метками вершин и ребер, а также выделенный кратчайший путь.

```python
graph.draw_graph(shortest_path)
```

Вы также можете использовать другие методы класса Graph, такие как:

- get_distances: возвращает список расстояний между всеми вершинами в графе.
- get_nodes: возвращает список всех вершин графа.
- get_outgoing_edges: возвращает список вершин, с которыми у заданной вершины есть связь.
- value: возвращает длину между двумя вершинами.
- calculate_distance: вычисляет расстояние между двумя координатами точек.

## Пример

Вот пример использования этого кода для создания и отрисовки графа, а также нахождения кратчайшего пути между двумя вершинами:

```python
"""Пример использования"""
# импорт самого класса
from main import Graph
# сами координаты
coordinates = [
    (1, 1.5),
    (4, 1.5), (15, 1.5),
    (15, 6.5), (12, 6.5),
    (8, 6.5), (4, 6.5),
    (1, 6.5), (1, 16),
    (6, 16), (7, 13),
    (9, 13), (12, 14),
    (16, 14), (16, 18),
    (12, 18), (9, 18),
    (9, 19.5), (8, 19.5),
    (8, 22), (6, 20),
    (4, 20), (4, 22),
    (10, 22), (10, 24),
    (16, 24), (15, 24)
]

# пути куда можно пойти
connections = {
    (1, 1.5): [(4, 1.5)],
    (4, 1.5): [(15, 1.5), (4, 6.5)],
    (15, 1.5): [(15, 6.5)],
    (15, 6.5): [(12, 6.5)],
    (12, 6.5): [(8, 6.5)],
    (8, 6.5): [(7, 13), (4, 6.5), (9, 13)],
    (7, 13): [(9, 13)],
    (9, 13): [(9, 18)],
    (9, 18): [(9, 19.5), (12, 18)],
    (9, 19.5): [(8, 19.5)],
    (8, 19.5): [(8, 22)],
    (8, 22): [(10, 22)],
    (10, 22): [(10, 24)],
    (10, 24): [(15, 24)],
    (12, 18): [(16, 18)],
    (16, 18): [(16, 24)],
    (16, 24): [(15, 24)],
    (7, 13): [(6, 16)],
    (6, 16): [(6, 20)],
    (6, 20): [(4, 20)],
    (4, 20): [(4, 22)],
    (4, 22): [(8, 22)],
    (4, 6.5): [(1, 6.5)],
    (1, 6.5): [(1, 16)],
    (1, 16): [(6, 16)],
    (12, 14): [(16, 14), (12, 18)],
    (16, 14): [(16, 18)],
}

# вызываются методы для нахождения кратчайшего пути и отрисовки графа с этим путем.
graph = Graph(coordinates, connections)
shortest_path = graph.dijkstra_algorithm((1, 1.5), (15, 24))
graph.draw_graph(shortest_path)
print(graph.value((1, 1.5), (4, 1.5)))
print(graph.get_nodes())
print(graph.construct_graph())
```
