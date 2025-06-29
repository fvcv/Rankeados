import java.util.Scanner; // Importa a classe Scanner para ler a entrada do usuário

public class CalculadoraRankeadas {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Cria um objeto Scanner para entrada

        System.out.println("--- Calculadora de Partidas Ranqueadas ---");

        // Laço de repetição para permitir múltiplos cálculos ou sair
        boolean continuar = true;
        while (continuar) {
            System.out.println("\nPor favor, insira a quantidade de vitórias do jogador:");
            int vitorias = scanner.nextInt(); // Lê a quantidade de vitórias

 System.out.println("Agora, insira a quantidade de derrotas do jogador:");
            int derrotas = scanner.nextInt(); // Lê a quantidade de derrotas

            // Chama a função para calcular o nível e o saldo
            String resultadoNivel = calcularNivel(vitorias, derrotas);

            // Exibe a mensagem final
            System.out.println(resultadoNivel);

            // Pergunta ao usuário se deseja continuar
            System.out.println("\nDeseja calcular o nível de outro jogador? (sim/nao)");
            String resposta = scanner.next();
            if (!resposta.equalsIgnoreCase("sim")) {
                continuar = false; // Se a resposta não for "sim" (ignorando maiúsculas/minúsculas), encerra o laço

                 String resultadoNivel = calcularNivel(vitorias, derrotas);

            // Exibe a mensagem final
            System.out.println(resultadoNivel);

            // Pergunta ao usuário se deseja continuar
            System.out.println("\nDeseja calcular o nível de outro jogador? (sim/nao)");
            String resposta = scanner.next();
            if (!resposta.equalsIgnoreCase("sim")) {
                continuar = false; // Se a resposta não for "sim" (ignorando maiúsculas/minúsculas), encerra o laço
            }
        }

scanner.close(); // Fecha o Scanner para liberar recursos
        System.out.println("\nObrigado por usar a calculadora de Rankeadas! Até a próxima!");
    }

    /**
     * Calcula o saldo de Rankeadas e determina o nível do jogador.
     *
     * @param vitorias Quantidade de vitórias do jogador.
     * @param derrotas Quantidade de derrotas do jogador.
     * @return Uma String contendo o saldo de vitórias e o nível do jogador.
     */
    public static String calcularNivel(int vitorias, int derrotas) {
        int saldoVitorias = vitorias - derrotas; // Calcula o saldo de vitórias

        String nivel; // Variável para armazenar o nível

        // Estruturas de decisão para determinar o nível com base no saldo
        if (saldoVitorias < 0) { // Saldo negativo, mas vamos considerar como "Ferro" se for <= 10

           nivel = "Ferro";
        } else if (saldoVitorias <= 10) {
            nivel = "Ferro";
        } else if (saldoVitorias <= 20) {
            nivel = "Bronze";
        } else if (saldoVitorias <= 50) {
            nivel = "Prata";
        } else if (saldoVitorias <= 80) {
            nivel = "Ouro";
        } else if (saldoVitorias <= 90) {
            nivel = "Diamante";
        } else if (saldoVitorias <= 100) {
            nivel = "Lendário";
        } else {
ivel = "Imortal"; // Mais de 100 vitórias
        }

        // Retorna a mensagem formatada
        return "O Herói tem um saldo de " + saldoVitorias + " e está no nível de " + nivel + ".";
    }
}
        
