/* 4ª Lista de Exercícios de Estruturas de Dados I
   Aluno: Jonatas Fontele Dourado
   Professor: Evilasio Costa Junior
   Ciencias da Computação - UECE */
#include <stdio.h>
#include <stdlib.h>
#define MAX 5000

int opc, i, posicao, direcao;

typedef struct{ //Questao 1
    char nome[30];
    int cpf [11];
}Cliente;
typedef struct{ //Serve para as questoes 2, 3 e 4
    Cliente cliente[MAX];
    int tamanho;
}ListaSequencial;

int menu(); //Questao 1
int menu1(); //menu para Listas estaticas

void criaLista(ListaSequencial *l); //Serve para os itens 'a' das questoes 2, 3 e 4
void inserirFim(ListaSequencial *l, Cliente c); //Serve para os itens 'b' das questoes 3 e 4
void inserir(ListaSequencial *l, Cliente c, int posicao); //Questão 2 item 'b'
void removerFim(ListaSequencial *l); //Questao 3 item 'c'
void remover(ListaSequencial *l, int posicao); //Serve para os itens 'c' das questoes 2 e 4
Cliente retornarInicio(ListaSequencial *l, int posicao); //Questao 2 item 'd'
Cliente retornarFim(ListaSequencial *l, int posicao); //Questao 2 item 'd'
int buscarInicio(ListaSequencial *l, Cliente c);
int buscarFim(ListaSequencial *l, Cliente c);
int informarTamanho(ListaSequencial *l);
void listarElementos(ListaSequencial *l, int direcao);
void destruirLista(ListaSequencial *l); //Serve para os itens 'd' das questoes 3 e 4 e item 'e' da questao 2

int main(){
    ListaSequencial *l = (ListaSequencial*) malloc(sizeof(ListaSequencial));
    Cliente *c = (Cliente*) malloc(sizeof(Cliente));
	if(!l){
        printf("Sem memoria disponivel!\n");
		exit(1);
	}
	do{
		opc = menu();
		opcao(l, c, posicao);
	}
	while(opc!=2);{
	free(l);
	free(c);
	}
	return 0;
}

int menu(){ //menu principal
    system("cls");
    printf("Bem vindo ao trabalho do aluno Jonatas Fontele Dourado. Digite o numero da opcao que deseja:\n");
    printf("1 - Criar Lista Estatica.\n");
    printf("2 - Sair.\n");
    scanf("%d", &opc);
    return opc;
}
int menu1(){ //menu para Lista estatica
    system("cls");
    printf("Digite o numero da operacao que deseja:\n");
    printf("1 - Inserir em qualquer posicao.\n");
    printf("2 - Remover em qualquer posicao.\n");
    printf("3 - Retornar elemento.\n");
    printf("4 - Buscar elemento.\n");
    printf("5 - Retornar tamanho da lista.\n");
    printf("6 - Listar todos os elementos da lista.\n");
    printf("7 - Destruir lista.\n");
    printf("8 - Sair.\n");
    scanf("%d", &opc);
    return opc;
}

void opcao(ListaSequencial *l, Cliente c, int posicao, int posicao1, int posicao2){
    switch(opc){
        case 1:
            criaLista(l);
            do{
                menu1();
                switch(opc){
                    case 1:
                        printf("Insira a posicao a partir de 0 e o nome.\n");
                        scanf("%d", &posicao);
                        scanf("%s", &c.nome);
                        inserir(l, c, posicao);
                        break;
                    case 2:
                        printf("Insira a posicao a partir de 0.\n");
                        scanf("%d", &posicao);
                        remover(l, posicao);
                        break;
                    case 3:
                        printf("Insira a posicao a partir de 0.\n");
                        scanf("%d", &posicao);
                        retornarInicio(l, posicao);
                        break;
                    case 4:
                        printf("Insira o nome que deseja buscar.\n");
                        scanf("%s", &c.nome);
                        buscarInicio(l, c);
                        break;
                    case 5:
                        informarTamanho(l);
                        break;
                    case 6:
                        printf("Digite 1 para sentido crescente ou 2 para decrescente.\n");
                        scanf("%d", &direcao);
                        listarElementos(l, direcao);
                        break;
                    case 7:
                        destruirLista(l);
                        break;
                    case 8:
                        break;
                    default:
                        system("cls");
                        printf("Esta nao e um opcao possivel, por favor escolha outro numero.");
                        getch();
                        break;
                }
            }
            while(opc != 8);
            free(l);
            break;
        case 2:
            break;
        default:
            system("cls");
            printf("Esta nao e um opcao possivel, por favor escolha outro numero.");
            getch();
            break;
    }
}
//Estatica
void criaLista(ListaSequencial *l){
    l->tamanho = 0;
    printf("Lista estatica vazia criada.\n");
    getch();
}
void inserirFim(ListaSequencial *l, Cliente c){
    l->cliente[l->tamanho] = c;
    l->tamanho = l->tamanho + 1;
    printf("%s inserido no fim, posicao ultrapassou o fim da lista ou ja existia um elemento.\n",c.nome);
    getch();
}
void inserir(ListaSequencial *l, Cliente c, int posicao){
    if(posicao >= l->tamanho)
        inserirFim(l,c);
    else{
        for(i = l->tamanho-1; i>=posicao;i--)
            l->cliente[i+1] = l->cliente[i];
        l->cliente[posicao] = c;
        l->tamanho = l->tamanho+1;
        printf("%s inserido na posicao %d.\n",c.nome, posicao);
        getch();
    }
}
void removerFim(ListaSequencial *l){
    printf("Ultimo elemento removido. O tamanho da lista diminuiu.\n");
    l->cliente[l->tamanho - 1].nome == "";
    l->tamanho = l->tamanho - 1;
    getch();
}
void remover(ListaSequencial *l, int posicao){
    if(posicao >= l->tamanho-1)
        removerFim(l);
    else{
        printf("%s removido da posicao %d. O tamanho da lista diminuiu.\n",l->cliente[posicao].nome, posicao);
        for(i = posicao; i<l->tamanho-1; i++)
            l->cliente[i] = l->cliente[i+1];
        l->tamanho = l->tamanho-1;
        getch();
    }
}
Cliente retornarInicio(ListaSequencial *l, int posicao){
    int i = 0;
    while(i<posicao && i<l->tamanho)
        i++;
    printf("%s esta nessa posicao.", l->cliente[i].nome);
    getch();
}
Cliente retornarFim(ListaSequencial *l, int posicao){
    int i = l->tamanho-1;
    while(i>l->tamanho-posicao && i>=0){
        i--;
    }
    return l->cliente[i];
    getch();
}
int buscarInicio(ListaSequencial *l, Cliente c){
    int indice = -1;
    for(i = 0; i<l->tamanho; i++){
        if(!strcmp(l->cliente[i].nome, c.nome)){
            indice  = i;
            printf("%s encontrado na posicao %d.", c.nome, indice);
            break;
        }
    }
    getch();
}
int buscarFim(ListaSequencial *l, Cliente c){
    int indice = -1;
    for(i = l->tamanho-1; i>=0; i--){
        if(!strcmp(l->cliente[i].nome, c.nome)){
            indice  = i;
            break;
        }
    }
    printf("%s Encontrado na posicao %d.", c.nome, indice);
    getch();
}
int informarTamanho(ListaSequencial *l){
    printf("\nTamanho da lista: %d.\n", l->tamanho);
    getch();
}
void listarElementos(ListaSequencial *l, int direcao){
    system("cls");
    if(direcao == 1){
        for(i = 0; i < l->tamanho; i++)
            printf("%s\n", l->cliente[i].nome);
    }
    else{
        for(i = l->tamanho-1; i >= 0; i--)
            printf("%s\n", l->cliente[i].nome);
    }
    getch();
}
void destruirLista(ListaSequencial *l){
    l->tamanho = 0;
    printf("Lista destruida.");
    getch();
}
