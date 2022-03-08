# DesafioCapgeminiRepo
Desafio de Programação - Capgmini


// Questão 01
// ----------------
// Escreva um algoritmo que mostre na tela uma escada de tamanho n utilizando o caractere * e espaços. 
// A base e altura da escada devem ser iguais ao valor de n. A última linha não deve conter nenhum espaço.

// Triangulo invertido

        System.out.println("Informe o tamanho do Triangulo: ");
        int y = x.nextInt();
        int z = (y-1);

        for(int i=0; i<y; i++){
            System.out.print("\n");

                for(int j=0; j<=y; j++){
                        if(j<=z){
                            System.out.print(" ");  
                        }else{
                            System.out.print("*");
                        }

                }

            if(z>0){
                System.out.print("\n");
            }
            z--;
        }


//Triangulo normal

        int z = 1;
        for(int i=0; i<y; i++){
            System.out.print("\n");
                for(int j=0; j<z; j++){
                        if(z<=y){
                            System.out.print("*");  
                        }
                }
            
            z++;
        }


        System.out.println("\n");
        x.close();


   

// Questão 02
//---------------
// Débora se inscreveu em uma rede social para se manter em contato com seus amigos.
// página de cadastro exigia o preenchimento dos campos de nome e senha, porém a senha precisa ser forte. 
// O site considera uma senha forte quando ela satisfaz os seguintes critérios:
// Possui no mínimo 6 caracteres.
// Contém no mínimo 1 dígito.
// Contém no mínimo 1 letra em minúsculo.
// Contém no mínimo 1 letra em maiúsculo.
// Contém no mínimo 1 caractere especial. Os caracteres especiais são: !@#$%^&*()-+


        System.out.println();
        System.out.println("Sistema de cadastro - NOME e SENHA");

        String userName;
        String userPassword;
        boolean keyExit = false;

        System.out.println("Informe o nome do Usuario: ");
        userName = x.nextLine();
            
        System.out.println("Informe a senha: ");
        userPassword = x.nextLine();

        while(keyExit == false){

            int cntDigit=0, cntMaius=0, cntMinus=0;

            for(int i=0; i<userPassword.length(); i++){

                // Filtrar o que é necessário para ter uma senha válida.

                if(userPassword.charAt(i) >= 'A' && userPassword.charAt(i) <= 'Z'){
                    cntMaius+=1;
                }
                if(userPassword.charAt(i) >= 'a' && userPassword.charAt(i) <= 'z'){
                    cntMinus+=1;
                }
                if(userPassword.charAt(i) >= '0' && userPassword.charAt(i) <= '9'){
                    cntDigit+=1;
                }
                    
                                
            }    
                    
            if(cntDigit!=0 && cntMaius!=0 && cntMinus!=0 && userPassword.length() > 6){

                System.out.println("Senha VÁLIDA");
                keyExit = true;

            }else{

                System.out.println("Senha INVÁLIDA ");
                
                if(cntMaius == 0){
                    System.out.println("Falta letra Mauiscula");
                }
                if(cntMinus == 0){
                    System.out.println("Falta letra Minuscula");
                }
                if(cntDigit == 0){
                    System.out.println("Falta digitos Númericos");
                }
                if(userPassword.length() <= 6){
                    System.out.println("Colocar + que 06 caracteres");
                }
                    
                System.out.println("Informe uma senha Válida: ");
                userPassword = x.nextLine();
               
            }

           System.out.println("Usário: " + userName + "Senha validada: " + userPassword);
           x.close();

        }


// Questão 03
// ------------------
// Duas palavras podem ser consideradas anagramas de si mesmas se as letras de uma palavra 
// podem ser realocadas para formar a outra palavra. Dada uma string qualquer, 
// desenvolva um algoritmo que encontre o número de pares de substrings que são anagramas.

// Exemplo: OVO - Saida: 02

        String palavra;
        
        System.out.println("Informe a palavra desejada: ");
        palavra = x.nextLine();
        int tamPalavra = palavra.length();
        
        int cntLetraIgual=0, y=1;
        int calcFatTotal=0, calcFatNumRepetido=0;
        
        // Separar as letras iguais

        for(int i=0;i<tamPalavra;i++){ 
            System.out.print("I - " + palavra.charAt(i) + " ");
            System.out.print(" J - ");
            for(int j=y;j<tamPalavra;j++){
                System.out.print(palavra.charAt(j) + " ");
                    if(palavra.charAt(i) == palavra.charAt(j)){
                        cntLetraIgual+=1;
                    }
            }
            y+=1;
            System.out.println();
        }

        if(palavra.charAt(0) == palavra.charAt(tamPalavra-1) && tamPalavra<=3){
            cntLetraIgual++;
        }

        System.out.println("Quantidade de letras " + tamPalavra);
        System.out.println("Quantidade de LETRAS Iguais: " + cntLetraIgual);

        // Calcular a quantidade de palavras que podem ser formadas no total de letras
        
       calcFatTotal=tamPalavra;
        for(int k=tamPalavra-1;k>0;k--){
            calcFatTotal = (calcFatTotal*k);
        }

        // Imprimir a quantidade de ANAGRAMAS, com letras repetidas ou sem.
        
        if(cntLetraIgual == 0){
            System.out.println("Quantidade de ANAGRAMAS: " + calcFatTotal);
        }else{
            calcFatNumRepetido=cntLetraIgual;
            for(int l=cntLetraIgual-1; l>0;l--){
                calcFatNumRepetido = (calcFatNumRepetido*l);
            }
            System.out.println("Quantidade de ANAGRAMAS com Letras Repetidas: " + (calcFatTotal/calcFatNumRepetido));
        }
        

    }

}


