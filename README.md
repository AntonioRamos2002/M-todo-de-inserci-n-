#include <iostream>
using namespace std;

// Función para ordenar el arreglo utilizando el método de inserción
void insertionSort(int arr[], int n, bool ascending) {
    int i, key, j;
    for (i = 1; i < n; i++) {
        key = arr[i];
        j = i - 1;

        // Mover elementos del arreglo que son mayores o menores que key a una posición adelante de su posición actual
        if (ascending) {
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
        } else {
            while (j >= 0 && arr[j] < key) {
                arr[j + 1] = arr[j];
                j--;
            }
        }
        arr[j + 1] = key;
    }
}

// Función principal del programa
int main() {
    int arr[10];
    bool ascending;

    // Pedir al usuario que ingrese los valores del arreglo
    cout << "Ingrese 10 valores enteros separados por espacios:" << endl;
    for (int i = 0; i < 10; i++) {
        cin >> arr[i];
    }

    // Pedir al usuario que especifique el orden
    char order;
    cout << "¿En qué orden desea ordenar los valores? (A para ascendente, D para descendente): ";
    cin >> order;

    // Determinar si se debe ordenar en orden ascendente o descendente
    if (order == 'A' || order == 'a') {
        ascending = true;
    } else if (order == 'D' || order == 'd') {
        ascending = false;
    } else {
        cout << "Opción no válida. Saliendo del programa.";
        return 1;
    }

    // Ordenar el arreglo utilizando el método de inserción
    insertionSort(arr, 10, ascending);

    // Imprimir el arreglo ordenado
    cout << "Arreglo ordenado:";
    if (ascending) {
        for (int i = 0; i < 10; i++) {
            cout << " " << arr[i];
        }
    } else {
        for (int i = 9; i >= 0; i--) {
            cout << " " << arr[i];
        }
    }

    return 0;
}
`
