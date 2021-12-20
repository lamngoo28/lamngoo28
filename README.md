#include <iostream>

using namespace std;

bool kiemtra(int k, int res) {
    if (res == k) {
        return false;
    }
    int count1 = 0;
    for (int i = 1; i <=k; i++) {
        if (k % i == 0) {
            count1++;
        }
    }
    int count2 = 0;
    for (int i = 1; i <= res; i++) {
        if (res % i == 0) {
            count2++;
        }
    }
    if (count1!= 2 || count2 != 2) {
        return false;
    }
    return true;

}
int main() {
    int N;
    cin >> N;
    int arr[N];
    for (int i = 0; i < N; i++) {
        int b[N];
        int x = 0;
        cin >> arr[i];
        int p = arr[i];
        for (int k = 1; k < p; k++) {
            int m = k;
            int tmp;
            int res = 0;
            while (m > 0) {
                tmp = m % 10;
                res = res * 10 + tmp;
                m = m / 10;
            }
            if (res < p && kiemtra(k, res) == true) {
                b[x] = k;
                x++;
            }
        }
        for (int j = 0; j < sizeof(b); j++) {
            cout << b[j] << " ";
        }
        cout << endl;
    }

}
