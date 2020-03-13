#include <iostream>
#include <vector>
#include <algorithm>
#include <iomanip> //SetPrecision

using namespace std;

///////////////////////////////////

struct Produto{

    string nome;
    float preco;
    string descricao;
};

bool comparaPreco(Produto a, Produto b){

    return a.preco < b.preco;
}

void setItens(Produto &t){

    bool s;
    string desc;
    
    cout << "\n\n -Descreva itens importantes: (Descrição)\n";
    do{
        string item;

        cout << "  Digite um item: ";
        getline(cin, item);

        desc += "    -" + item + ";\n";

        cout << "\n-Mais um item? (1-sim / 0-nao): ";
        cin >> s;
        cin.ignore();
    }while(s);

    t.descricao = desc;
}

///////////////////////////////////

int main(){

    float preco_medio = 0;
    int quantidade = 0;
    cout <<fixed<<setprecision(2); //Para os pre�os sa�rem ao estilo ".00"
    vector<Produto> lista;
    bool saida;


    system("clear");
    cout << "\n\n -Comparador de produtos-";
    do{
        Produto temp;

        cout << "\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n";

        cout << " Qual produto deseja colocar na lista? ";
        getline(cin, temp.nome);

        cout << "\n Qual o preco? R$ ";
        cin >> temp.preco;

        cin.ignore();

        setItens(temp);

        lista.push_back(temp);

        cout << "\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n";

        cout << "-Mais um produto? (1-sim / 0-nao): ";
        cin >> saida;
        cin.ignore();
    }while(saida);

/////////////////////////////////// Lista

    system("clear");
    cout << "~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n\n lista completa:\n";
    for(auto e : lista){

        cout << "\n-Produto: "<< e.nome;
        cout << ";\n Preco: R$ "<< e.preco;
        cout << ";\n  Descricao:\n"<< e.descricao<< "\n";
    }

/////////////////////////////////// Pre�o medio

    for(auto e : lista){
        preco_medio += e.preco;
        quantidade++;
    }
    preco_medio = preco_medio/quantidade;
    cout << "\n-Preco medio: R$ "<< preco_medio<<";\n";

/////////////////////////////////// Iterator para maior/menor pre�o

    vector<Produto>::iterator it;

// Maior pre�o
    it = max_element(lista.begin(), lista.end(), comparaPreco);
    cout << "\n-Maior preco: "<< it->nome<<", R$"<< it->preco<<";\n";

// Menor pre�o
    it = min_element(lista.begin(), lista.end(), comparaPreco);
    cout << "\n-Menor preco: "<< it->nome<<", R$"<< it->preco<<";\n";

    cout << "\n~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n";

    return 0;
}
