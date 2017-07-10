# hackerrank-ElectronicsShop
Solution for the problem Electronics Shop
// Coded by Pankaj Kumar
// 06:05 PM July 10,2017

#include <bits/stdc++.h>

using namespace std;

int getMoneySpent(vector < int > keyboards, vector < int > drives, int s){
    int n=keyboards.size();
    int m=drives.size();
    int res=0;
    for(int i=0;i<n;i++){
        for(int j=0;j<m;j++){
            if((keyboards[i]+drives[j])> res && (keyboards[i]+drives[j]) <= s )
                res=(keyboards[i]+drives[j]);
}
    }
    if(res==0)
        return -1;
    else
        return res;
}

int main() {
    int s;
    int n;
    int m;
    cin >> s >> n >> m;
    vector<int> keyboards(n);
    for(int keyboards_i = 0; keyboards_i < n; keyboards_i++){
       cin >> keyboards[keyboards_i];
    }
    vector<int> drives(m);
    for(int drives_i = 0; drives_i < m; drives_i++){
       cin >> drives[drives_i];
    }
    //  The maximum amount of money she can spend on a keyboard and USB drive, or -1 if she can't purchase both items
    int moneySpent = getMoneySpent(keyboards, drives, s);
    cout << moneySpent << endl;
    return 0;
