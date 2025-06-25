# Senai_LLP_EnumGen_Pedido

import java.util.ArrayList;
import java.util.Scanner;

public class PedidoEnum {
    
    // Enum de categorias
    enum Categoria {
        ALIMENTO,
        ELETRONICO,
        OUTROS
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        ArrayList<String> descricoes = new ArrayList<>();
        ArrayList<Integer> quantidades = new ArrayList<>();
        ArrayList<Categoria> categorias = new ArrayList<>();

        System.out.println("Cadastro de itens do pedido:");

        while (true) {
            System.out.print("\nDescrição do item (vazio para encerrar): ");
            String descricao = scanner.nextLine();

            if (descricao.isEmpty()) {
                break;
            }

            System.out.print("Quantidade do item: ");
            int quantidade = Integer.parseInt(scanner.nextLine());

            System.out.println("Escolha a categoria:");
            System.out.println("1. Alimento");
            System.out.println("2. Eletrônico");
            System.out.println("3. Outros");
            System.out.print("Categoria (1-3): ");
            int opcao = Integer.parseInt(scanner.nextLine());

            Categoria categoriaSelecionada;
            if (opcao == 1) {
                categoriaSelecionada = Categoria.ALIMENTO;
            } else if (opcao == 2) {
                categoriaSelecionada = Categoria.ELETRONICO;
            } else {
                categoriaSelecionada = Categoria.OUTROS;
            }

            descricoes.add(descricao);
            quantidades.add(quantidade);
            categorias.add(categoriaSelecionada);
        }

        // Impressão final do pedido
        System.out.println("\n--- ITENS DO PEDIDO ---");
        for (int i = 0; i < descricoes.size(); i++) {
            System.out.printf("%s %s %d%n", categorias.get(i), descricoes.get(i), quantidades.get(i));
        }
    }
}
