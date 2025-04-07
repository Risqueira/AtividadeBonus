# AtividadeBonus
# Questao 1
```java
package teste;

import java.util.Calendar;
import java.util.Scanner;

/**
 *
 * 12. Faça um algoritmo que leia dois valores inteiros A e B se os valores
 * forem iguais deverá se somar os dois, caso contrário multiplique A por B. Ao
 * final de qualquer um dos cálculos deve-se atribuir o resultado para uma
 * variável C e mostrar seu conteúdo na tela. Obs.: escreva o algoritmo na folha
 *
 * @author Henrique
 */
public class Teste {

    public static void main(String[] args) {

        int idade, anoNascimento, anoIngresso, tempoTrabalhado;
        String codigoEmpregado;
        Scanner ler = new Scanner(System.in);
        Calendar hoje = Calendar.getInstance();
        
        System.out.println("Digite o seu codigo de empregado:");
        codigoEmpregado= ler.nextLine();
        System.out.println("Digite seu ano de nascimento:");
        anoNascimento= ler.nextInt();
        System.out.println("Digite o ano que se ingressou na empresa:");
        anoIngresso= ler.nextInt();
if(idade<18){
            System.out.println("DE MENOR");
            return;
        }
        if(anoNascimento>=anoAtual){
            System.out.println("INVALIDO");
            return;
        }
        if(anoIngresso<=anoNascimento){
            System.out.println("INVALIDO");
            return;
        }
        if(tempoTrabalhado>=idade&&tempoTrabalhado<=idade){
            System.out.println("INVALIDO");
            return;
        }
        
        //calculos de tempo
        int anoAtual = hoje.get(Calendar.YEAR);
        idade = anoAtual-anoNascimento;
        tempoTrabalhado = anoAtual-anoIngresso;
        
        if(idade>=65 || tempoTrabalhado>=30){
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ " anos Requerer aposentadoria");
        }else if(idade>=60 && tempoTrabalhado>=25){
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ " anos Requerer aposentadoria");
        }else{
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ "  anos Não querer aposentadoria");
        }
        

        
    }
}
```
# Questao 2
```java
package exer2;

import java.text.DecimalFormat;
import java.util.Scanner;

/**
 * Um posto está vendendo combustíveis com a seguinte tabela de descontos:
 * Escreva um algoritmo que leia o número de litros vendidos e o tipo de
 * combustível (codificado da seguinte forma: 1 - álcool, 2 - gasolina), calcule
 * e imprima o valor a ser pago pelo cliente sabendo-se que o preço do litro da
 * gasolina é R$ 5,20 e o preço do litro do álcool é R$ 4,90.
 *
 * @author Henrique
 */
public class Exer2 {

    public static void main(String[] args) {

        double precoGaso, precoAlcool, litros, precoLitros;
        String tipoCombustivel;
        Scanner ler = new Scanner(System.in);
        DecimalFormat decimal = new DecimalFormat("0.00");

        precoAlcool = 4.90;
        precoGaso = 5.20;
        System.out.println("Digite 1 para alcool ou digite 2 para gasolina:");
        tipoCombustivel = ler.nextLine();
        System.out.println("Quantos litros você abasteceu?");
        litros = ler.nextDouble();

        if (tipoCombustivel.equals("1") && litros <= 20) {
            precoLitros = (precoAlcool * 0.97) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));
        } else if (tipoCombustivel.equals("1") && litros > 20) {
            precoLitros = (precoAlcool * 0.95) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));
        } else if (tipoCombustivel.equals("2") && litros <= 20) {
            precoLitros = (precoGaso * 0.96) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));
        } else if (tipoCombustivel.equals("2") && litros > 20) {
            precoLitros = (precoGaso * 0.94) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));
        }

    }

}
```
```
