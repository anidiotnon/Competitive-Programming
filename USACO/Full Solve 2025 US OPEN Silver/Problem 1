#include <iostream>
#include <vector>
#include <cmath>

using namespace std;

void solve() {
    int m;
    int k;
    int origM = 0;

    cin >> m >> k;

    vector<int> res;
    origM = m;
    int smallestBit = 0;
    int subAmt = 0;

    for (int i = 4; i >= 0; i--) { // checking bits of k
        if (k & (1 << i)) {
            smallestBit = i;

            subAmt = (1 << i);
            subAmt = (1 << subAmt) - 1;

            //cout << subAmt << endl;
            m -= subAmt;

            res.push_back(subAmt);
        }
    }
    if (m < 0) {
        cout << -1 << endl;

        return;
    }
    if (m % 2 == 1) {
        if (subAmt <= m and m < 3) {
            m -= subAmt;
            res[res.size() - 1] *= 2;

            if (m < 0) {
                cout << -1 << endl;

                return;
            }
        }
        else {
            res.push_back(1);
            res.push_back(2);

            m -= 3;

            if (m < 0) {
                cout << -1 << endl;

                return;
            }
        }
    }
    //cout << "M: " << m << endl;
    m /= 2;
    while (m > 0) {
        smallestBit = (m & -m);

        //cout << "lowbit: " << smallestBit << endl;
        res.push_back(smallestBit);
        res.push_back(smallestBit);

        m -= smallestBit;
    }
    if (res.size() > 100) {
        cout << -1 << endl;

        return;
    }
    cout << res.size() << endl;
    for (int i = 0; i < res.size() - 1; i++) {
        cout << res[i] << " ";
    }
    cout << res[res.size() - 1] << endl;
}

int main()
{
    ios::sync_with_stdio(false);
    cin.tie(0);

    int t;

    cin >> t;

    while (t--) {
        solve();
    }
}
