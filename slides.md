---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://images.unsplash.com/photo-1547637589-f54c34f5d7a4?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1920&q=80
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: fade-out
# use UnoCSS
css: unocss
---

# Heap Binario
Equilibro perfecto entre tiempo y espacio

<div class="abs-br m-6 flex gap-2">
  <a href="https://www.geeksforgeeks.org/binary-heap/" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <simple-icons-geeksforgeeks/>
  </a>
  <a href="https://www.cs.usfca.edu/~galles/visualization/Heap.html" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <file-icons-sandbox/>1
  </a>
  <a href="https://visualgo.net/en/heap" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <file-icons-sandbox/>2
  </a>
</div>
---
layout: image-right
image: /DeepinScreenshot_select-area_20230318193052.png
---
# Heap Binario
Intro

Un `heap binario` es una estructura de datos que permite a los usuarios acceder, agregar y eliminar elementos de manera eficiente siguiendo una orden muy específico.

<br>

Las dos propiedades más importantes de un heap binario son:
- Propiedad estructural
- Propiedad de orden

---

# Propiedades del Heap Binario
Propiedad estructural y propiedad de orden

1. Es un árbol binario completo: todos los niveles del árbol están completamente llenos, excepto posiblemente el último, que se llena de izquierda a derecha.

2. Cumple la propiedad de orden del heap: para cada nodo `i`, el valor del nodo es siempre mayor (o menor) que los valores de sus hijos.


<div class="container flex justify-center items-center">
  <img src="/compTree.png" class="w-120">
</div>

---

# Tipos de Heap Binarios
Max-Heap | Min-Heap

- **Max Heap**: Los valores de los nodos son mayores o iguales que los de sus hijos. El nodo raíz contiene el elemento máximo.

- **Min Heap**: Los valores de los nodos son menores o iguales que los de sus hijos. El nodo raíz contiene el elemento mínimo.

<div class="container flex justify-center items-center">
  <img src="/DeepinScreenshot_select-area_20230319113821.png" class="w-150">
</div>

---

# Operaciones principales
Insertar, eliminar y extraer

- `insert`: Inserta un nuevo elemento en el heap.
- `delete`: Elimina y retorna el elemento máximo (o mínimo) del heap.
- `peek`: Retorna el elemento máximo (o mínimo) del heap sin eliminarlo.

---

# Inserción en Heap Binario
Proceso de inserción

Para insertar un elemento en un heap binario, se agrega al final y se reorganiza (flota) el heap para mantener la propiedad de heap (orden).

<div class="flex flex-col">
  <div class="container flex justify-center">
    <img class="absolute z-0 w-150" v-click src="/row-1-column-1.png" alt="Imagen 1">
   </div>
  <div class="container flex justify-center">
    <img class="absolute z-10 w-150" v-click src="/row-2-column-1.png" alt="Imagen 2">
   </div>
  <div class="container flex justify-center">
    <img class="absolute z-20 w-150" v-click src="/row-3-column-1.png" alt="Imagen 3">
   </div>
</div>

---

# Eliminación en Heap Binario
Proceso de eliminación

Para eliminar un elemento en un heap binario, se elimina el elemento máximo (o mínimo) y se reorganiza (hunde) el heap para mantener la propiedad de heap (orden).

<div class="flex flex-col">
  <div class="container flex justify-center">
    <img class="absolute z-0 w-150" v-click src="/DeepinScreenshot_select-area_20230319133108.png" alt="Imagen 1">
   </div>
  <div class="container flex justify-center">
    <img class="absolute z-10 w-150" v-click src="/DeepinScreenshot_select-area_20230319133140.png" alt="Imagen 2">
   </div>
  <div class="container flex justify-center">
    <img class="absolute z-20 w-150" v-click src="/DeepinScreenshot_select-area_20230319133209.png" alt="Imagen 3">
   </div>
   <div class="container flex justify-center">
    <img class="absolute z-20 w-150" v-click src="/DeepinScreenshot_select-area_20230319133243.png" alt="Imagen 4">
   </div>
</div>

---

# Complejidad de operaciones
The Big O

Las operaciones principales en un heap binario tienen las siguientes complejidades de tiempo:

- `insert`: O(1)cp / O(log n)pc
- `delete`: O(log n)
- `peek`: O(1)

Esto permite a los heaps binarios realizar inserciones y eliminaciones de manera eficiente, especialmente en comparación con otras estructuras de datos, como listas ordenadas o árboles de búsqueda binaria desequilibrados.

---

# O(1)cp en inserción
¿Cómo es posible?

En la mayoría de los casos, el número de intercambios que se deben realizar es pequeño. La altura del árbol es `log_2(n)`, donde n es el número de nodos. Sin embargo, la probabilidad de que se necesiten `log_2(n)` intercambios es baja, ya que es más probable que el elemento que estamos insertando no tenga que recorrer todo el camino hasta la raíz.

> **vease:** [Average Case Analysis of Heap Building by Repeated Insertion](https://web.archive.org/web/20160205023201/http://www.stats.ox.ac.uk/__data/assets/pdf_file/0015/4173/heapbuildjalg.pdf)

En términos más matemáticos, si analizamos el número de intercambios esperados en la inserción, resulta ser una serie geométrica que converge a una suma finita, lo que implica un tiempo promedio constante.

> `1 + 1/2 + 1/4 + 1/8 + ... = 2`

---

# Aplicaciones
TADs y algoritmos

Los heaps binarios tienen varias aplicaciones en la informática, incluyendo:

- Implementación de colas de prioridad.
- Algoritmo de Dijkstra para encontrar el camino más corto en un grafo.
- Algoritmo de Prim para encontrar el árbol de expansión mínima en un grafo.

---

# Ventajas y desventajas
¿Cuándo usarlo?

**Ventajas:**

- Operaciones rápidas de inserción y eliminación.
- Eficiente en el uso de memoria.
- Implementación sencilla.

**Desventajas:**

- No es óptimo para buscar un elemento específico que no sea el máximo (o mínimo).
- No es el mejor para operaciones de búsqueda en general, en comparación con otras estructuras de datos como árboles AVL.
- Tiene tamaño fijo, por lo que no es posible aumentar o disminuir el tamaño del heap (al menos no de manera eficiente).

---
layout: cover
background: https://images.unsplash.com/photo-1484417894907-623942c8ee29?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1920&q=80
---

# El array

---
layout: image-right
image: /binaryheap.png
---

# El array 
Como representación de un heap binario

Un heap binario puede ser representado de manera eficiente como un arreglo unidimensional.
<br><br>
👉 Esta representación aprovecha la naturaleza del árbol binario completo (propiedad estructural) y permite acceder fácilmente a los elementos y sus relaciones en el heap.

---
layout: image-right
image: /Same_Picture2.png
---

# Ventajas 
De la representación como arreglo

- Eficiente en términos de espacio, ya que no se requieren punteros o referencias adicionales.
- Acceso rápido a los nodos y sus relaciones utilizando las fórmulas de índices.
- Fácil de implementar y entender.

---

# Relación entre índices
Formulas

Dado un nodo en el índice `i` del arreglo, podemos calcular los índices de sus hijos y su padre utilizando las siguientes fórmulas:

- Hijo izquierdo: `2i`
- Hijo derecho: `2i + 1`
- Padre: `i / 2`

Estas fórmulas permiten navegar rápidamente entre los nodos del heap sin la necesidad de punteros o referencias adicionales.

> **Nota**: Estas fórmulas solo funcionan si la raíz del árbol está en el índice 1.
> Si la raíz del árbol está en el índice 0, las fórmulas se modifican de la siguiente manera:
> - Hijo izquierdo: `2i + 1`
> - Hijo derecho: `2i + 2`
> - Padre: `(i - 1) / 2`

---

# Implementación
c++

```cpp {all|3|43-46|6-8|15-23|20-22|22|49-54|50|51|52|26-36|31|32|33|34|56-64|57|58|59|60|61|62} {maxHeight:'400px'}
#include <iostream>

template <typename T>
class BinaryHeap {
public:
    BinaryHeap(int capacity) : size(0), capacity(capacity) {
        heap = new T[capacity + 1];
    }

    ~BinaryHeap() {
        delete[] heap;
    }

    // Insertar un elemento en el heap
    void insert(T value) {
        if (size == capacity) {
            std::cout << "Heap is full" << std::endl;
            return;
        }
        size++;
        heap[size] = value;
        swim(size);
    }

    // Eliminar el elemento máximo
    T removeMax() {
        if (isEmpty()) {
            std::cout << "Heap is empty" << std::endl;
            return T();
        }
        T maxValue = heap[1];
        swap(1, size);
        size--;
        sink(1);
        return maxValue;
    }

    // Verificar si el heap está vacío
    bool isEmpty() {
        return size == 0;
    }

private:
    T* heap;
    int size;
    int capacity;

    // Mantener la propiedad de max-heap
    void swim(int index) {
        while (index > 1 && heap[index / 2] < heap[index]) {
            swap(index, index / 2);
            index = index / 2;
        }
    }

    void sink(int index) {
        while (2 * index <= size) {
            int j = 2 * index;
            if (j < size && heap[j] < heap[j + 1]) j++;
            if (heap[index] >= heap[j]) break;
            swap(index, j);
            index = j;
        }
    }

    // Intercambiar dos elementos en el heap
    void swap(int i, int j) {
        T temp = heap[i];
        heap[i] = heap[j];
        heap[j] = temp;
    }
};
```

---
layout: cover
background: https://images.unsplash.com/photo-1503551723145-6c040742065b-v2?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80
---

# Cola de prioridad

---

# Cola de prioridad
TAD

Una `cola de prioridad` es un TAD que permite almacenar elementos con una prioridad asociada.
<br>
Las operaciones principales en una cola de prioridad son:

- `insert`: Inserta un elemento con una clave de prioridad.
- `delete`: Elimina y retorna el elemento con la clave de prioridad más alta.
- `peek`: Retorna el elemento con la clave de prioridad más alta sin eliminarlo.

---

# Implementaciones de cola de prioridad
Diferentes implementaciones

Existen varias formas de implementar una cola de prioridad, incluyendo:

- Lista ordenada
- Lista no ordenada
- Árbol AVL
- Heap binario

Cada implementación tiene sus propias ventajas y desventajas en términos de complejidad de tiempo y espacio.
<br><br>

¿Qué ordenes tiene cada una? 🤔

---

# Cola de prioridad con Heap binario
Implementación

Un heap binario es una implementación popular y eficiente de una cola de prioridad. Veamos cómo se relacionan las operaciones principales de una cola de prioridad con las de un heap binario:

- `insert`: Se corresponde con la operación `insert` del heap binario.
- `delete`: Se corresponde con la operación `delete` (eliminar máximo/mínimo) del heap binario.
- `peek`: Se corresponde con la operación `peek` del heap binario.
<br><br>
> ⚠️ Es normal la confusión entre cola de prioridad y heap binario, ya que ambos tiene metodos similares.

---

# Ventajas de usar Heap binario
👍

- Las operaciones `insert` y `delete` tienen una complejidad de tiempo O(log n) (peor caso), lo que es más rápido que las listas ordenadas y no ordenadas.
- El espacio requerido es O(n), que es más eficiente que las listas.
- La implementación es sencilla y fácil de entender.

---

# Desventajas de usar Heap binario
👎

- No es óptimo para buscar elementos específicos que no sean el máximo (o mínimo).
- Otras estructuras de datos, como árboles AVL, pueden ofrecer mejores tiempos de búsqueda para ciertas aplicaciones.

---

# Cola de prioridad extendida
Level up 🚀

Una cola de prioridad extendida es una cola de prioridad con las siguientes operaciones adicionales:

- `changePririty`: Cambia la prioridad de un elemento.
- `delete`: Elimina un elemento (cualquiera) de la cola de prioridad.

<br><br>

¿Cómo lo hacemos con un heap? 😵

---
layout: center
class: text-center
---

# Heap + Tabla de hash

<div class="container flex justify-center items-center">
  <img v-click src="/1_cY0Cga9s_jrNklMk0FI0uw.gif" class="w-120">
</div>

---

# Cola de prioridad extendida
Implementación

La idea es usar la tabla de hash para saber la posición de cada elemento en el heap. De esta forma, podemos compensar la falta de búsqueda en un heap binario.
<br><br>
¿Qué ordenes tiene ahora? 🤔
<br><br>
> ⚠️ Se deben modificar las operaciones `insert` y `delete` para que funcionen con la tabla de hash.

---
layout: center
class: text-center
---

# Learn More

[Resumen](https://publish.obsidian.md/algoritmos/Estructuras+de+datos/Heap) · [Geeks For Geeks](https://www.geeksforgeeks.org/binary-heap/)
