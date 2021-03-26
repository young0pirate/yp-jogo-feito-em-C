// Autor: Damião Facundo
// Data: 26/03/2021
//  Hora: 7:22 pm
// Versão: 1.1
// https://www.github.com/young0pirate/
//Mini jogo 
#include <stdio.h>
#include <stdlib.h>
#
int main(int argc, char *argv[])
{
	int x, n1, n[2], i,  op;
	srand(time(NULL));
	
	int cont = 5, cont1 = 10,  acert = 0, err = 0, acert1= 0, err1 = 0, acert2 = 0, err2 = 0;
	
	puts("FAÇA SUA ESCOLHA:");
	puts("+++++++++++++++++++++++++++++++++++++++++++++++++++++");
	puts("OPÇÃO 1 ->> JOGAR CONTRA O SISTEMA (1 JOGADOR APENAS)\nOPÇÃO 2 ->> JOGAR CONTRA O SISTEMA (2 JOGADORES)");
		puts("+++++++++++++++++++++++++++++++++++++++++++++++++++++");
		scanf("%d",&op);
		system("cls || clear");
		switch(op){
			
			//ESCOLHA UM - 1 JOGADOR
			case 1:
	do
	{
			puts("*****************************************************");
			
	puts("Os números a serem acertados variam de 0 à 50. Boa sorte com as 5 tentativas que tens a disposição! :D");
	
	puts("*****************************************************");
	--cont;
	puts("Digite um número: ");
	scanf("%d",&n1);
	x = rand() % 51;
	if(n1 != x)
	{
		system("clear || cls");
		++err;
		printf("O número que você digitou é: %d\nE o do computador foi......: %d\n",n1, x);
	puts("Ohhh!! Infelizmente você errou! T_T");
	
	printf("\nRestam-lhe: %d tentativas...\n\n",cont);
	}
	
	else
	{
		system("clear || cls");
		++acert;
		printf("O número que você digitou é: %d\nE o do computador foi......: %d\n",n1, x);
	puts("Você acertou! Parabéns!! <3");
	
	printf("\nRestam-lhe: %d tentativas...\n\n",cont);
	}
	
	system("pause");
	system("clear || cls");
	}while(cont > 0);
	
	//ESTATÍSTICA DO JOGO
	
	puts("GAME OVER!");
	puts("@@@@@@@@@@@@@@@@@@@@");
	
	puts("Estatística do jogo: ");
	printf("\nAcertos: %d\nErros..: %d\n",acert, err);
	puts("@@@@@@@@@@@@@@@@@@@@\n");
	puts("°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°");
	
	  //FELICITAR O JOGADOR
	puts("Não fique desmoralizado por não teres conseguido acertar sequer uma. O jogo é realmente difícil!\nE se tu conseguiu acertar algumas, estás de parabéns :B.\nAgora, se tu acertou todas, tu és um \"Deus\" da aleatoriedade :P");
		puts("°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°");
	
	  //CASO TENHA ACERTADO 50%
	if(acert == 5)
	puts("\n\nParabéns! Você é incrível, seu nível de acertos superou as expectativas!!\nSua taxa de acertos  foi de \'100%\' ");
	
 //CASO NÃO TENHA CHEGADO AOS 50%
	else
	puts("\n\nSeu nível de acertos está bem na média. Nada mau!!\nSua taxa de acertos  foi de \'50%\' ");
	puts("\n\nPrecisas melhor sua classificação urgentemente!!\nSua taxa de acertos  foi abaixo dos  \'50%\' ");
	break;
	//FIM UM JOGADIR 1
	
	//OPÇÃO 2 - 2 JOGADORES
	
	case 2:
	do
	{
			puts("****************************************************");
			
	puts("Os números a serem acertados variam de 0 à 100. Boa sorte com as 10 tentativas que tens a disposição! :D");
	
	puts("*****************************************************");
	--cont1;
	
	x = rand() % 101;
   for(i = 0; i <= 2-1; i++){
   	printf("%dº jogador digite um número: ",i+1);
   	scanf("%d",&n[i]);
   }
   system("clear || cls");
   
   //SE AMBOS ERRARAM
   if(n[0] != x && n[1] != x){
   	for( int d = 0; d <= 2-1; d++){
   	printf("%dº jogador digitou: %d\n",d+1,n[d]);
   	}
   	printf("E o computador sorteou: %d\n",x);       puts("INFELIZMENTE AMBOS ERRARAM!! :(");
   	err1++;
   	err2++;
   }
   
   //SE AMBOS ACERTARAM
   else if(n[0] == x && n[1] == x){
   	for( int d = 0; d <= 2-1; d++){
   	printf("%dº jogador digitou: %d\n",d+1,n[d]);
   	}
   	printf("E o computador sorteou: %d\n",x);
   	puts("PARABÉNS AMBOS ACERTARAM!! CONTINUEM ASSIM! :)");
   	acert1++;
   	acert2++;
   }
   
   //SE O 1º ACERTOU E O 2º ERROU
   else if(n[0] == x && n[1] != x){
   	for( int d = 0; d <= 2-1; d++){
   	printf("%dº jogador digitou: %d\n",d+1,n[d]);
   	}
   	printf("E o computador sorteou: %d\n",x);       printf("1º JOGADOR ACERTOU :)\n 2º JOGADOR ERROU! :(\n");
   	acert1++;
   	err2++;
   }
   
   //SE O 1º ERROU E O 2º ACERTOU
   else if(n[0] != x && n[1] == x){
   	for( int d = 0; d <= 2-1; d++){
   	printf("%dº jogador digitou: %d\n",d+1,n[d]);
   	}
   	printf("E o computador sorteou: %d\n",x);       err1++;
   	acert2++;
   }
   
   //CASO CHEGUE AO MEIO DO JOGO
   if(cont1 == 5){
  puts("\n\nALERTA! ♦");
  puts("*****************************************************");
   puts("SE AINDA NÃO ACERTARAM NENHUMA VEZ, MELHOR\nREPENSERAM VOSSAS ESTRATÉGIAS! :@.\nJÁ ESTAMOS A MEIO DO JOGO");
   puts("*****************************************************");
   }
   
   //NÚMERO DE TENTATIVAS
   printf("\n\nRESTA-VOS %d TENTATIVAS...\n\n ",cont1);
   system("pause");
	system("clear || cls");
	}while(cont1 > 0);
	
	//ESTATÍSTICA DOS JOGADORES
	system("clear || cls");
	puts("GAME OVER!");
	puts("@@@@@@@@@@@@@@@@@@@@@@");
	
	puts("Estatística do jogo: ");
	printf("\nNúmero de vezes que o\n1º jogador acertou: %d\nSeus erros foram..: %d\n",acert1, err1);
	printf("\nNúmero de vezes que o\n2º jogador acertou: %d\nSeus erros foram..: %d\n",acert2, err2);
	puts("@@@@@@@@@@@@@@@@@@@@@@\n");
	puts("°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°");
	
	//MOTIVAR JOGADOR
	puts("Não fiquem desmoralizados por não terem conseguido acertar sequer uma. O jogo é realmente difícil!\nE se tu conseguiu acertar algumas, estás de parabéns :B.\nAgora, se tu acertou todas, tu és um \"Deus\" da aleatoriedade :P");
		puts("°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°");
		
		//FELICITAÇÕES FINAIS
		if(acert1 > acert2)
		puts("\n\n\t1º JOGADOR SAIU VITORIOSO NESSA PARTIDA. PARABÉNS!");
		else if(acert1 <  acert2)
		puts("\n\n\tt2º JOGADOR SAIU VITORIOSO NESSA PARTIDA. PARABÉNS!");
		else if(acert1 ==  acert2)
		puts("\n\n\t1º JOGADOR E 2º JOGADOR SAIRAM EMPATADOS!");
	break;
		}
}
