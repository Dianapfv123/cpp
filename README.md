# codigo que solicita un numero y te dice que digito es numero primo y cual no


#include <iostream>
#include <cmath>
using namespace std;

bool par(int num) {
    return num % 2 == 0;
}

bool primo(int num) {
    if (num<= 1)
        return false;

    int sis= sqrt(num);
    for (int a= 2; a<=sis; a++) {
        if (num%a == 0)
            return false;
    }
    return true;
}

void esprimo_espar(int num) {
    while (num != 0) {
        int digito = num % 10;
        cout<<digito<<" ";
                
        if (par(digito)) {
            cout << "es par";
        } else {
            cout << "es impar";
        }

        if (primo(digito)) {
            cout << " y es primo." << endl;
        } else {
            cout << " y no es primo." << endl;
        }
cout<<"............................."<<endl;     
        num=num/10; 
    }
}

int main() {
	int num;
	do{
    cout << "Ingrese un numero: ";
    cin >> num;

    if (num<= 0) {
        cout << "El numero debe ser mayor a cero." <<endl;
    }
}while(num<=0);
    
    esprimo_espar(num);
    
    return 0;
}
