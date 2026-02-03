[Travesuras en el hotel de Hilbert](https://aceptaelreto.com/problem/statistics.php?id=800)

El programa té truco, cal saber que:

> Un número tiene número impar de divisores <=> es cuadrado perfecto

```c#
#include <iostream>
#include <cmath>
using namespace std;

void BucleDeEstat(long long entrada){
    // Un número tiene número impar de divisores <=> es cuadrado perfecto
    long long raiz = sqrt((double)entrada);
    // Verificar la raíz
    bool esCuadrado = (raiz * raiz == entrada);
    cout << (esCuadrado ? "ENCENDIDA" : "APAGADA") << "\n";
}

bool casoDePrueba() {

    if (!cin)
        return false;
    else {
        long long entrada;
        cin >> entrada;
        if (!cin) return false;
        BucleDeEstat(entrada);
        return true;
    }

}

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(nullptr);
    while(casoDePrueba()) {
    }
  
    return 0;
}
```