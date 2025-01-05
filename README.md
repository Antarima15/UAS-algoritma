# UAS-algoritma
Pengumpulan UAS algoritma 

1. SOURCH CODE UNTUK BINARY-SEARCH:



#include <iostream>

Using namespace std;



Int binarySearch(int array[], int x, int low, int high) {

  

  // Ulangi hingga pointer low dan high bertemu

  While (low <= high) {

    Int mid = low + (high – low) / 2;



    If (x == array[mid])

      Return mid;



    If (x > array[mid])

      Low = mid + 1;



    Else

      High = mid – 1;

  }



  Return -1;

}



Int main(void) {

  Int array[] = {3, 4, 5, 6, 7, 8, 9};

  Int x = 4;

  Int n = sizeof(array) / sizeof(array[0]);

  Int hasil = binarySearch(array, x, 0, n – 1);

  If (hasil == -1)

    Printf(“Elemen tidak ditemukan”);

  Else

    Printf(“Elemen ditemukan pada indeks %d”, hasil);

}







SOURCH CODE UNTUK LINEAR-SEARCH:

#include <iostream>

Using namespace std;



Int cari(int array[], int n, int x) {



  // Mencari elemen dalam array secara berurutan

  For (int i = 0; i < n; i++)

    If (array[i] == x)

      Return i;

  Return -1;

}



Int main() {

  Int array[] = {2, 4, 0, 1, 9};

  Int x = 1;

  Int n = sizeof(array) / sizeof(array[0]);



  Int hasil = cari(array, n, x);



  (hasil == -1) ? cout << “Elemen tidak ditemukan” : cout << “Elemen ditemukan pada indeks: “ << hasil;

}




2. C++: Merge Sort



#include <iostream>

#include <vector>

#include <string>

using namespace std;



struct Order {

    int id;

    int time;

};



void merge(vector<Order>& orders, int left, int mid, int right) {

    int n1 = mid - left + 1, n2 = right - mid;

    vector<Order> L(n1), R(n2);



    for (int i = 0; i < n1; i++) L[i] = orders[left + i];

    for (int i = 0; i < n2; i++) R[i] = orders[mid + 1 + i];



    int i = 0, j = 0, k = left;

    while (i < n1 && j < n2) {

        if (L[i].time <= R[j].time)

            orders[k++] = L[i++];

        else

            orders[k++] = R[j++];

    }

    while (i < n1) orders[k++] = L[i++];

    while (j < n2) orders[k++] = R[j++];

}



void mergeSort(vector<Order>& orders, int left, int right) {

    if (left < right) {

        int mid = left + (right - left) / 2;

        mergeSort(orders, left, mid);

        mergeSort(orders, mid + 1, right);

        merge(orders, left, mid, right);

    }

}



int main() {

    vector<Order> orders = {{1, 5}, {2, 1}, {3, 3}, {4, 2}};

    mergeSort(orders, 0, orders.size() - 1);



    for (const auto& order : orders)

        cout << "ID: " << order.id << ", Time: " << order.time << endl;

    return 0;

}






