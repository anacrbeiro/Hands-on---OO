1. public class Lista {
        public static void main(String[] args) {
     ArrayList<String> produtos = new ArrayList<>();
     produtos.add("Banana");
     produtos.add("Abacaxi");
     produtos.add("Mamao");
     produtos.add("Leite");
     produtos.add("Arroz");
     
        
      System.out.println(produtos);
      
      System.out.println("Primeiro produto: " + produtos.get(0));
      System.out.println("Segundo produto: " + produtos.get(1));
      System.out.println("Terceiro produto: " + produtos.get(2));
      System.out.println("Quarto produto: " + produtos.get(3));
      System.out.println("Quinto produto: " + produtos.get(4));
    
}
}


     -------------------------------------------------------------
     
     2. import java.util.ArrayList;

public class Notas {

    public static void main(String[] args) {

        ArrayList<Double> notas = new ArrayList<>();

        notas.add(8.0);
        notas.add(7.5);
        notas.add(6.0);
        notas.add(9.0);

        double soma = 0;

        for (Double nota : notas) {
            soma += nota;
        }

        double media = soma / notas.size();

        System.out.println("Média da turma: " + media);

        if (media >= 7) {
            System.out.println("A turma foi aprovada.");
        } else {
            System.out.println("A turma foi reprovada.");
        }
    }
}

     -------------------------------------------------------------
     
     3. import javaapplication5;

public class Presenca {

    public static void main(String[] args) {

        HashSet<String> alunos = new HashSet<>();

        alunos.add("Ana");
        alunos.add("João");
        alunos.add("Maria");
        alunos.add("Ana");  // repetido
        alunos.add("João"); // repetido

        System.out.println("Alunos presentes: " + alunos);
        System.out.println("Quantidade de alunos: " + alunos.size());
    }
}

     -------------------------------------------------------------

     4. import javaapplication5;

public class Alunos {

    public static void main(String[] args) {

        HashMap<Integer, String> alunos = new HashMap<>();

        // Cadastrar alunos
        alunos.put(101, "Ana");
        alunos.put(102, "João");
        alunos.put(103, "Maria");

        // Buscar aluno pela matrícula
        System.out.println("Aluno da matrícula 102: " + alunos.get(102));

        // Remover aluno pela matrícula
        alunos.remove(103);

        // Mostrar todos os alunos cadastrados
        System.out.println("Alunos cadastrados:");
        System.out.println(alunos);
    }
}

     -------------------------------------------------------------
     
5. import javaapplication5;
import java.util.Queue;

public class FilaClientes {

    public static void main(String[] args) {

        Queue<String> clientes = new LinkedList<>();

        // Adicionar 5 clientes
        clientes.add("Ana");
        clientes.add("João");
        clientes.add("Maria");
        clientes.add("Carlos");
        clientes.add("Pedro");

        // Mostrar próximo cliente
        System.out.println("Próximo a ser atendido: " + clientes.peek());

        // Atender 2 clientes
        clientes.poll();
        clientes.poll();

        // Mostrar fila atualizada
        System.out.println("Fila atualizada: " + clientes);
    }
}

     -------------------------------------------------------------
     
     6. public class Livro {

    int codigo;
    String titulo;
    String autor;
    boolean disponivel;

    public Livro(int codigo, String titulo, String autor) {
        this.codigo = codigo;
        this.titulo = titulo;
        this.autor = autor;
        this.disponivel = true;
    }
}

/////////////////////////// MAIN \\\\\\\\\\\\\\\\\\\\\\\\\\\\

import javaapplication5;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        ArrayList<Livro> livros = new ArrayList<>();

        int opcao;

        do {

            System.out.println("\n1 - Cadastrar livro");
            System.out.println("2 - Listar livros");
            System.out.println("3 - Emprestar livro");
            System.out.println("4 - Devolver livro");
            System.out.println("0 - Sair");

            opcao = sc.nextInt();

            if (opcao == 1) {

                System.out.print("Código: ");
                int codigo = sc.nextInt();
                sc.nextLine();

                System.out.print("Título: ");
                String titulo = sc.nextLine();

                System.out.print("Autor: ");
                String autor = sc.nextLine();

                livros.add(new Livro(codigo, titulo, autor));

            } else if (opcao == 2) {

                for (Livro livro : livros) {

                    System.out.println("Código: " + livro.codigo);
                    System.out.println("Título: " + livro.titulo);
                    System.out.println("Autor: " + livro.autor);
                    System.out.println("Disponível: " + livro.disponivel);
                    System.out.println();
                }

            } else if (opcao == 3) {

                System.out.print("Código do livro: ");
                int codigo = sc.nextInt();

                for (Livro livro : livros) {

                    if (livro.codigo == codigo) {

                        if (livro.disponivel) {
                            livro.disponivel = false;
                            System.out.println("Livro emprestado!");
                        } else {
                            System.out.println("Livro indisponível!");
                        }
                    }
                }

            } else if (opcao == 4) {

                System.out.print("Código do livro: ");
                int codigo = sc.nextInt();

                for (Livro livro : livros) {

                    if (livro.codigo == codigo) {
                        livro.disponivel = true;
                        System.out.println("Livro devolvido!");
                    }
                }
            }

        } while (opcao != 0);

        sc.close();
    }
}

     -------------------------------------------------------------
     
     7. public class Pedido {

    int numero;
    String cliente;
    String item;
    double valor;
    String status;
}

/////////////////////////// MAIN \\\\\\\\\\\\\\\\\\\\\\\\\\\\

import javaapplication5;

public class Main {

    public static void main(String[] args) {

        ArrayList<Pedido> pedidos = new ArrayList<>();

        Pedido p1 = new Pedido();
        p1.numero = 1;
        p1.cliente = "Ana";
        p1.item = "Hamburguer";
        p1.valor = 25.0;
        p1.status = "PENDENTE";

        Pedido p2 = new Pedido();
        p2.numero = 2;
        p2.cliente = "João";
        p2.item = "Pizza";
        p2.valor = 40.0;
        p2.status = "PREPARANDO";

        pedidos.add(p1);
        pedidos.add(p2);

        for (Pedido pedido : pedidos) {
            System.out.println("Pedido: " + pedido.numero);
            System.out.println("Cliente: " + pedido.cliente);
            System.out.println("Item: " + pedido.item);
            System.out.println("Valor: R$ " + pedido.valor);
            System.out.println("Status: " + pedido.status);
            System.out.println();
        }

        double total = 0;

        for (Pedido pedido : pedidos) {
            total += pedido.valor;
        }

        System.out.println("Valor total: R$ " + total);
    }
}
