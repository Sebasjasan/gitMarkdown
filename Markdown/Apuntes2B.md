# Apuntes Segundo Bimestre

## Clase 1: 16 de enero Intro a C++

Hola mundo con c++:

```c++
#include <iostream>
using namespace std;

int main (){
    // Con "using namespace std;" evitamos poner std :: antes del cout
    cout << "hola mundo";
    return 0;
}
```

## Clase 2: 17 de enero C++

Uso de variables locales y parametros

```c++
#include <iostream>
using namespace std;

void Hola(string nombre){ //parametros: La variable local dentro de los parentesis de "void Hola ()"
    //variable local
    //string nombre
    cout << "Hola " << nombre << endl;
}
int main (){
    Hola ("Sebas");
    Hola ("Pepe");
    return 0;
}
```

## Clase 3: 18 de enero Practica

Uso de la funcion switch para hacer un menu

```c++
#include <iostream>
using namespace std;

int main (){
    int opc;
    cout << "|--------MENU--------|"          << endl
         << "1.- Numeros pares"     << endl 
         << "2.- Numeros impares"   << endl
         << "3.- Serie de signos"   << endl
         << "0.- Salir"             << endl
         << "Opcion: ";
    cin >> opc;
    switch (opc)
    {
    case 0:
        exit(0);
        break;
    case 1:
        cout << endl << "Elegiste la opcion numeros pares" << endl;
        break;
    case 2:
        cout << endl << "Elegiste la opcion numeros impares" << endl;
        break;
    case 3:
        cout << endl << "Elegiste la opcion serie de signos" << endl;
        break;
    }
    return 0;
}
```

## Clase 4: 20 de enero Series

Elaboración de series

```c++
#include <iostream>
using namespace std;
void pares(){
    int nroTernimos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroTernimos;
    for (int i = 0; i < nroTernimos; i++)
    {
        cout << i*2 << " "; 
    }
}

void impares(){
    int nroTernimos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroTernimos;
    for (int i = 0; i < nroTernimos; i++)
    {
        cout << i*2+1 << " "; 
    }
}

void serieSignos(){
    int nroSignos;
    cout << "Ingrese la cantidad de signos: ";
    cin  >> nroSignos;
    for (int i = 0; i < nroSignos; i++)
    {
        cout << "+" << " "; 
    }
}

int main (){
    pares();
    cout << endl;
    impares();
    cout << endl;
    serieSignos();
    cout << endl;

}
```

## Clase 5: 23 de enero Foro, do, while

Series con For, do while

```c++
#include <iostream>
using namespace std;
void paresFor(){
    int nroTernimos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroTernimos;
    for (int i = 0; i < nroTernimos; i++)
    {
        cout << i*2 << " "; 
    }
}
void paresWhile(){
    int nroTernimos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroTernimos;
    int i = 0;
    while ( i < nroTernimos)
    {
        cout << i*2 << " "; 
        i++;
    }
}
void paresDo(){
    int nroTernimos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroTernimos;
    int i = 0;
    do
    {
        cout << i*2 << " "; 
        i++;
    } while (i < nroTernimos);
    
}
int main (){
    paresFor();
    cout << endl;
    paresWhile();
    cout << endl;
    paresDo();
    cout << endl;
}
```

## Clase 6: 24 de enero For, do, while

Series con For, do while

```c++
#include <iostream>
using namespace std;
void serieSignosFor(){
    int nroSignos;
    cout << "Ingrese la cantidad de signos: ";
    cin  >> nroSignos;
    for (int i = 0; i < nroSignos; i++)
    {
        for (int r = 0; r <= i; r++)
        {
            cout << "+";
        }
        cout << " ";
    }
}
void serieSignosWhile(){
    int nroSignos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroSignos;
    int i = 0;
    while (i < nroSignos)
    {
        int r = 0;
        while (r <= i)
        {
            cout << "+";
            r++;
        }
        i++;
        cout << " ";
    }
}
void serieSignosDo(){
    int nroSignos;
    cout << "Ingrese la cantidad de terminos: ";
    cin  >> nroSignos;
    int i = 0;
    do
    {
        int r = 0;
        do
        {
            cout << "+";
            r++;
        } while (r <= i);
        i++;
        cout << " ";
        
    } while (i < nroSignos);
}
int main (){
    serieSignosFor();
    cout << endl;
    serieSignosWhile();
    cout << endl;
    serieSignosDo();
    cout << endl;
}
```

## Clase 7: 25 de enero Archivos

```c++
#include <iostream>
#include <fstream>
using namespace std;

void LeerArchivo(string pathFile)  
{
    string s;
    fstream f;
    f.open(pathFile, ios_base::in);
    if ( !f.is_open() ) 
        cout << "Error de abrir el archivo." << endl;
    else
        do 
        {
            getline( f, s );
            cout << s << endl;
            //getchar();  // Para presentar de uno en uno
        }while( !f.eof() );
    f.close();
}
void CrearArchivo(string pathFile)  
{
    string s;
    fstream f;

    cout << "Escibiendo en un archivo" << endl;
    f.open(pathFile, ios_base::out);
    //ios_base::in --> Solo lee, no agrega texto
    //ios_base::app --> Agrega texto
    //ios_base::out --> Escribe y borra el texto anterior
    if (f.is_open())
    {
        do
        {
            cout<< "(N = salir ) Ingresa un nombre: ";
            cin>>s;
            if (s!="N")
                f << s << endl;
        } while (s!="N");
    }
    f.close();
}

int main()
{
    //CrearArchivo("textfiles/ListaAlumnos.txt");
    LeerArchivo("textfiles/ListaAlumnos.txt");
    return 0;
}
```

## Clase 8: 27 de enero Matriz

```c++
#include <iostream>
using namespace std;

int main (){
    string matriz = "Hola mundo";
    cout << matriz[0];
}
```

## Clase 9: 30 de enero Matriz unidemensional, array

```c++
#include <iostream>
using namespace std;
void matrizImpar(int tf, int tc){
    int matriz [tf][tc];
    //encerar
    // for (int f = 0; f < tf; f++)
    //     for (int c = 0; c < tc; c++)
    //         matriz [tf][tc] = 0;
    for (int f = 0; f < tf; f++)
        for (int c = 0; c < tc; c++)
            if (f==0)
                matriz [f][c] = c*2;
            else if (f==1)
                matriz [f][c] = c*2+1;
            else
            matriz [f][c] = 0;
    //presentar
    for (int f = 0; f < tf; f++)
    {
        for (int c = 0; c < tc; c++)
            cout << matriz [f][c] << " ";
        cout << endl;
    }
}
int main(){
    int fila, columna;
    cout << "Ingresa el nro de filas: ";
    cin >> fila;
    cout << "Ingresa el nro de columnas: ";
    cin >> columna;
    matrizImpar(fila, columna);
}
```

## Clase 10: 31 de enero Matriz multidimensional

```c++
#include <iostream>
using namespace std;
void MatrizCaracteresG(int fila, int columna){
     char matriz[fila][columna];
 
    for(int f= 0; f < fila; f++){
        for( int c=0; c < columna; c++){
            matriz[f][c]='+';
        }
    }
    for(int f= 0; f < fila; f++){
        for( int c=0; c < columna; c++){
            cout<<matriz[f][c]<<" ";
        }
        cout<<endl;
    }
}
void showMatriz(char matriz[][2],int fila, int columna){
 
 for(int f= 0; f < fila; f++){
        for( int c=0; c < columna; c++){
            cout<<matriz[f][c]<<" ";
        }
        cout<<endl;
    }
}
void MatrizCaracteres(){
    int fila = 3;
    int columna = 2;
    char matriz[3][2]={  {'a' , 'b'}
                        ,{'c' , 'd'}
                        ,{'e' , 'f'}};
    showMatriz(matriz,fila,columna);
}
int main(void){
    MatrizCaracteres();
    //MatrizCaracteresG(5,2);
    return 0;
}
```

## Clase 11: 01 de febrero Teoria punteros

|   Conceptos  |
|---------|
|**Puntero:** Es una variable que almacena la direccion de memoria de otra variable, un puntero siempre se lo denota de la siguiente manera "*ptr".|
|**&num:** De esta forma se conoce la direccion de memoria de una variable|
|**ptr=&num:** ptr almacenara la direccion de num|
|***ptr:** ptr imprime lo qeu se encuentre en la direccion de memoria.|
|**ptr:** Imprime la direccion de memoria.|

## Clase 12: 03 de febrero Punteros ejemplo

Ejemplo del uso de punteros:

```c++
#include <iostream>
using namespace std;

int main(){

    int num = 20;
    int *ptr;

    cout << "\nSIN PUNTEROS" << endl;
    cout << "Numero: " <<num << endl; 
    cout << "Direccion de memoria: "<< &num << endl;

    ptr = &num;
    cout << "\nCON PUNTEROS" << endl;
    cout << "Numero: " << *ptr << endl; 
    cout << "Direccion de memoria: "<< ptr << endl;

    return 0;
}
```

## Clase 14: 07 de febrero Practica puntero

```c++
#include <iostream>
using namespace std;

int main(){
    int v[3];
    int *ptr;

    for (int i = 0; i < 3; i++)
    {
        v[i]=(i+1)*10;
        cout << v[i] << " ";
    }
    cout << endl;

    ptr = v;     //ptr=&v[0]

     for (int i = 0; i < 3; i++)
    {
        ptr[i]=i+10;
        cout << ptr[i] << " ";
    }
    cout << endl;
    return 0;
}
```

## Clase 15: 08 de febrero Matriz puntero

```c++
#include <iostream>
using namespace std;

void showArray(const int *a, int c){
    for (int i = 0; i < c; i++)
        cout<<a[i]<<"  ";
    cout<<endl;
}

int main() {
  int ai[]={1,3,5,7,9};
  int *p=ai;
  showArray(ai,5);
  
  int matrix[3][3]= { {1,2,3}, 
                      {4,5,6},
                      {7,8,9}};
  int (*ptr)[3] = matrix;
     
  for (int f=0; f < 3; f++) {
      //int *e = *ptr++;
      showArray(*ptr++,3);
      //for (int c = 0; c < 3; c++)
      //  cout<<*(e+c)<<"  ";
  }

 

  return 0;
}
```

## Clase 16: 13 de febrero Puntero matriz

```c++
#include <iostream>
using namespace std;
 
    int **crearMatrizMalloc(int f, int c){
        int **m=NULL;
        m = (int **) malloc(f*sizeof(int *)); // int ** guarda referencia
        for (int i = 0; i < f; i++)
            m[i] = (int *) malloc(c*sizeof(int));
        
        return m;
    }
    int **crearMatrizCalloc(int f, int c)
    {
        int **m=NULL;
        m = (int **) calloc(f, sizeof(int *));
        for (int i = 0; i < f; i++)
            m[i] = (int *) calloc(c, sizeof(int));
        
        return m;
    }
    int **crearMatrizNew(int f, int c)
    {
        int **m=NULL;
        m = new int*[f];
        for (int i = 0; i < f; i++)
            m[i] = new int[c];
 
        return m;
    }
    void showMatriz(int **pd, int f,int c)
    {
    for (int i = 0; i < f; i++)
    {
            for (int j = 0; j < c; j++)
                cout<< pd[i][j] <<"\t";   
            cout<< endl;
    }
    }
 
    int main()
    {
        int f = 0, c = 0;
        int **pd=NULL;
 
        cout<<"Ingresa fila y columnas de la matriz : ";
        cin>> f >> c;
    
        pd = crearMatrizNew(f,c);
 
        for (int i = 0; i < f; i++)
            for (int j = 0; j < c; j++)
                pd[i][j] = rand() % 10;  // genera randomicos hasta 10
        
        showMatriz(pd,f,c);
        return 0;
    }
```

## Clase 17: 14 de febrero Estructuras

Uso de la funcion struct

```c++
#include <iostream>
using namespace std;
struct Mascota{
    string nameMascota;
    int edadMascota;
};
struct Alumnos{
    string nombre;
    int edad;
    Mascota m;
};
int main(){
    Alumnos a1 = {"Sebas", 19, {"Negro", 4}};
    Alumnos a2 = {"Sophia", 4, {"Blanca", 3}};
    Alumnos lst[] = {a1, a2};
    // cout << "[+] Datos de alumno" << endl
    //      << "- Nombre: " << a1.nombre  << endl
    //      << "- Edad: "   << a1.edad    << endl
    //      << "- Nombre de la mascota: " << a1.m.nameMascota   << endl
    //      << "- Edad de la mascota: "   << a1.m.edadMascota     << endl
    //      << endl;
    for ( auto && a : lst)   // For inteligente 
    {
        cout << endl << "[+] Datos de alumno" << endl
         << "- Nombre: " << a.nombre  << endl
         << "- Edad: "   << a.edad    << endl
         << "- Nombre de la mascota: " << a.m.nameMascota   << endl
         << "- Edad de la mascota: "   << a.m.edadMascota     << endl
         << endl;
    }
    return 0;
}
```

## Clase 18: 15 de febrero Colas



## Clase 19: 17 de febrero Pilas

