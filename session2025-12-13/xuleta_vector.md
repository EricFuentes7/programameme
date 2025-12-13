# 🧠 CHULETA – `vector` en C++

## 📌 Qué es
- Contenedor **dinámico** (array redimensionable)
- Acceso aleatorio: **O(1)**
- Inserción al final: **O(1) amortizado**
- Inserción en medio: **O(n)**

👉 El contenedor más usado en competición

---

## 🔹 Declaración

```cpp
#include <iostream>
#include <vector>
#include <algorithm>  // para sort, reverse, find, etc.
#include <numeric>    // para accumulate
using namespace std;

vector<int> v;              // vector vacío
vector<int> v(n);           // n elementos inicializados a 0
vector<int> v(n, x);        // n elementos inicializados a x
vector<int> v = {1, 2, 3};  // inicialización con valores
```

---

## 🔹 Insertar elementos

### Al final
```cpp
v.push_back(5);
v.push_back(1);
v.push_back(3);
```

### En posición específica
```cpp
v.insert(v.begin() + i, x);  // inserta x en posición i
```

---

## 🔹 Acceder a elementos

```cpp
int x = v[0];        // primer elemento
int y = v[i];        // elemento i-ésimo
int z = v.front();   // primer elemento
int w = v.back();    // último elemento
```

---

## 🔹 Modificar elementos

```cpp
v[i] = 10;           // cambiar elemento i
v.front() = 20;      // cambiar primero
v.back() = 30;       // cambiar último
```

---

## 🔹 Eliminar elementos

### Del final
```cpp
v.pop_back();        // elimina último elemento
```

### En posición específica
```cpp
v.erase(v.begin() + i);              // elimina elemento i
v.erase(v.begin() + i, v.begin() + j); // elimina [i, j)
```

---

## 🔹 Tamaño

```cpp
int n = v.size();    // número de elementos
bool b = v.empty();  // true si está vacío
```

---

## 🔹 Limpiar

```cpp
v.clear();           // elimina todos los elementos
```

---

## 🔹 Recorrer

### Con índice
```cpp
for (int i = 0; i < v.size(); i++) {
    cout << v[i] << " ";
}
```

### Con range-based for
```cpp
for (int x : v) {
    cout << x << " ";
}
```

### Con iteradores
```cpp
for (auto it = v.begin(); it != v.end(); it++) {
    cout << *it << " ";
}
```

---

## 🔹 Ordenar

### Orden creciente
```cpp
sort(v.begin(), v.end());
```

### Orden decreciente
```cpp
sort(v.begin(), v.end(), greater<int>());
```

### Con comparador personalizado
```cpp
sort(v.begin(), v.end(), [](int a, int b) {
    return a > b;  // orden decreciente
});
```

---

## 🔹 Invertir

```cpp
reverse(v.begin(), v.end());
```

---

## 🔹 Búsqueda

### Lineal
```cpp
auto it = find(v.begin(), v.end(), x);
if (it != v.end()) {
    int pos = it - v.begin();  // posición encontrada
}
```

### Binaria (requiere vector ordenado)
```cpp
sort(v.begin(), v.end());  // primero ordenar
bool existe = binary_search(v.begin(), v.end(), x);
```

---

## 🔹 lower_bound y upper_bound (requiere ordenado)

### lower_bound(x)
👉 primer elemento **>= x**
```cpp
auto it = lower_bound(v.begin(), v.end(), x);
if (it != v.end()) {
    cout << *it;
}
```

### upper_bound(x)
👉 primer elemento **> x**
```cpp
auto it = upper_bound(v.begin(), v.end(), x);
```

---

## 🔹 Mínimo y máximo

```cpp
int mn = *min_element(v.begin(), v.end());
int mx = *max_element(v.begin(), v.end());
```

---

## 🔹 Suma de elementos

```cpp
long long suma = accumulate(v.begin(), v.end(), 0LL);
```

---

## 🔹 Eliminar duplicados (requiere ordenado)

```cpp
sort(v.begin(), v.end());
v.erase(unique(v.begin(), v.end()), v.end());
```

---

## 🔹 Redimensionar

```cpp
v.resize(n);        // redimensiona a n elementos
v.resize(n, x);     // rellena con x si crece
```

---

## 🔹 Reservar espacio (optimización)

```cpp
v.reserve(n);       // reserva memoria para n elementos
```

---

## 🔹 Vector 2D (matriz)

```cpp
int filas = 3, cols = 4;
vector<vector<int>> matriz(filas, vector<int>(cols, 0));

// Acceder
matriz[i][j] = 5;

// Recorrer
for (int i = 0; i < filas; i++) {
    for (int j = 0; j < cols; j++) {
        cout << matriz[i][j] << " ";
    }
    cout << endl;
}
```

---

## 🔹 Vector de pairs

```cpp
vector<pair<int, int>> v;
v.push_back({1, 2});
v.push_back(make_pair(3, 4));

// Acceder
int a = v[0].first;
int b = v[0].second;

// Ordenar por primer elemento (por defecto)
sort(v.begin(), v.end());

// Ordenar por segundo elemento
sort(v.begin(), v.end(), [](auto& a, auto& b) {
    return a.second < b.second;
});
```

---

## 🔥 Patrones PRO

### Leer n elementos
```cpp
int n;
cin >> n;
vector<int> v(n);
for (int& x : v) cin >> x;
```

### Leer hasta EOF
```cpp
vector<int> v;
int x;
while (cin >> x) {
    v.push_back(x);
}
```

### Copiar vector
```cpp
vector<int> copia = v;           // copia completa
vector<int> copia(v.begin(), v.begin() + k);  // primeros k
```

---

## 📊 Comparativa rápida

| Operación | Complejidad |
|-----------|-------------|
| `v[i]` | O(1) |
| `push_back` | O(1) amortizado |
| `pop_back` | O(1) |
| `insert` | O(n) |
| `erase` | O(n) |
| `find` | O(n) |
| `sort` | O(n log n) |
| `binary_search` | O(log n) |
