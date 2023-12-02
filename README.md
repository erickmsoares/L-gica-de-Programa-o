/*Inclusão de bibliotecas a serem utilizadas para execução do programa*/
#include <iostream>
#include <cstdlib>
#include <locale.h>
#include <string.h>

using namespace std;

void nome(); /*função "design do programa" prototipada acima da função main (função principal);*/
int perfeito(int x); /*função que retornará se o número é perfeito, devidamente prototipada acima da função main (função principal);*/
int main (){ /*Função principal do programa*/
setlocale(LC_ALL, "Portuguese"); /*Convertendo para o idioma português; isto permitirá o uso de acentos!*/

  int execucao, num;
nome();
cout<<"\n\n";
system("pause");
do{
  do{
  system("cls");	
  cout<<"Informe um número natural maior que zero: ";
  cin>>num;
  if(num<=0){
  	cout<<"\n\nVocê digitou um número diferente do solicitado. Aperte qualquer tecla para digitar novamente!";
  	system("pause");
  }
  }while(num<=0); /*loop que garante o programa ser executado apenas se o número for maior que zero;*/
  perfeito(num); /*Chamando a função que retornará se o número inserido é ou não perfeito!*/
  cout<<"\nDeseja testar outro número? (1- sim/qualquer número- sair): ";
  cin>>execucao;
}while(execucao>0 && execucao <2);
system("pause");
return 0;
}

/*Função que representa o "design" inicial, ou, nome do programa!*/
void nome(){
  int a;	
	  for(a=1;a<=58;a++){
		  cout<<"|";
    }
	  cout<<"\n| NUMEROS PERFEITOS! SABE DE QUE SE TRATA? VAMOS TESTAR! |\n";
    for(a=1;a<=58;a++){
		  cout<<"|";
	  }
}
/*Função que definirá a classificação do número: perfeito ou não*/
int perfeito(int x){

  int j, somaDiv=0, qtdDiv=0;

  for(j=1; j<=x/2; j++){
    if(x%j==0){
    	somaDiv+=j;
    	qtdDiv+=1;
    }
  }
  cout<<"\nO número possui "<<qtdDiv<<" divisores e a soma destes resulta "<<somaDiv<<". Logo..."<<"\n\n";
  if(somaDiv==x){
  	cout<<x<<" é um número perfeito, pois é igual a soma de seus divisores!\n";
  }else{
  	cout<<x<<" não é um número perfeito, pois é diferente da soma de seus divisores!\n";
  }
  return 1;
}
