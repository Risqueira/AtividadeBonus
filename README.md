# AtividadeBonus
# Questao 1
```java
package teste;

import java.util.Calendar;
import java.util.Scanner;

/**
 *
 * 1. Uma empresa quer verificar se um empregado está qualificado para a
aposentadoria ou não. Para estar em condições, um dos seguintes requisitos deve
ser satisfeito:
- Ter no mínimo 65 anos de idade.
- Ter trabalhado no mínimo 30 anos.
- Ter no mínimo 60 anos e ter trabalhado no mínimo 25 anos.
Com base nas informações acima, faça um algoritmo que leia: o número do
empregado (código), o ano de seu nascimento e o ano de seu ingresso na
empresa. O programa deverá escrever a idade e o tempo de trabalho do
empregado e a mensagem &#39;Requerer aposentadoria&#39; ou &#39;Não requerer&#39;..
 * @author Henrique
 */
public class Teste {

    public static void main(String[] args) {

       int idade, anoNascimento, anoIngresso, tempoTrabalhado, idadeIngressar;
        String codigoEmpregado;
        Scanner ler = new Scanner(System.in);
        Calendar hoje = Calendar.getInstance();
        
        System.out.println("Digite o seu codigo de empregado:");
        codigoEmpregado= ler.nextLine();
        System.out.println("Digite seu ano de nascimento:");
        anoNascimento= ler.nextInt();
        System.out.println("Digite o ano que se ingressou na empresa:");
        anoIngresso= ler.nextInt();

        //calculos de tempo
        int anoAtual = hoje.get(Calendar.YEAR);
        idade = anoAtual-anoNascimento;
        tempoTrabalhado = anoAtual-anoIngresso;
        idadeIngressar=anoIngresso-anoNascimento;
        
        //verificar se tem 18 anos 
        if(idade<18){
            System.out.println("INVALIDO");
            return;
        }
        //verificar se a pessoa nao ingressou antes de nascer
        if(anoIngresso<=anoNascimento){
            System.out.println("INVALIDO");
            return;
        }
        //verificar se a pessoa nao nasceu no futuro
        if(anoNascimento>=anoAtual){
            System.out.println("INVALIDO");
            return;
        }
        //verificar se não ingressou antes dos 18
        if(idadeIngressar<18){
            System.out.println("INVALIDO");
            return;
        }
        
        
        if(idade>=65 || tempoTrabalhado>=30){
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ " anos Requerer aposentadoria");
        }else if(idade>=60 && tempoTrabalhado>=25){
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ " anos Requerer aposentadoria");
        }else{
            System.out.println("O funcionario tem "+idade+" anos "+ "e trabalhou por "+ tempoTrabalhado+ " anos Não querer aposentadoria");
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

         if (tipoCombustivel.equals("1") && litros > 0 && litros <= 20) {
            precoLitros = (precoAlcool * 0.97) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));

        } else if (tipoCombustivel.equals("1") && litros > 20) {
            precoLitros = (precoAlcool * 0.95) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));

        } else if (tipoCombustivel.equals("2") && litros > 0 && litros <= 20) {
            precoLitros = (precoGaso * 0.96) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));

        } else if (tipoCombustivel.equals("2") && litros > 20) {
            precoLitros = (precoGaso * 0.94) * litros;
            System.out.println("o valor a ser pago é R$" + decimal.format(precoLitros));

        } else {
            System.out.println("Tipo de gasolina invalido ou valor de litros invalido");
        }
    }

}
```
```
