# HERANÇA 1

Primeiro exercício de Herança

## 🚀 Começando

Uma empresa possui como clientes pessoas físicas e jurídicas. Uma pessoa física possui nome, cpf, endereço e e-mail, enquanto uma pessoa jurídica possui nome, cnpj, endereço e email.

Há ainda a necessidade de cadastrar seus funcionários, onde cada funcionário possui nome, cpf, endereço e salário.

Crie classes adequadas para cada necessidade.

Teste as classes criando vários objetos.

### 📋 Pré-requisitos


class Pessoa { // Começo criando a classe base na qual as outras irão herdar
    String nome;
    String endereco;
    String email;

    public Pessoa(String nome, String endereco, String email) { 
        this.nome = nome;
        this.endereco = endereco;
        this.email = email;
    }

    String descricao() { // Criando o retorno que também será modelo para os outros
        return 
            "Nome: " + this.nome + "\n" + 
            "Endereço: " + this.endereco + "\n" +
            "Email: " + this.email + "\n";
    }
}


class PessoaFisica extends Pessoa { // Classe que herda de Pessoa a diferença é que adiciona o cpf por ser Pessoa Fisica
    String cpf;

    public PessoaFisica(String nome, String cpf, String endereco, String email) {
        super(nome, endereco, email);  // Chama o construtor da classe base puxando o modelo da super classse por isso utiliza o super
        this.cpf = cpf;
    }

  
    String descricao() {
        return super.descricao() + "Cpf: " + this.cpf + "\n";
    }
}


class PessoaJuridica extends Pessoa { // Classe que herda de Pessoa a diferença é que adiciona o cnpj por ser Pessoa Juridica
    String cnpj;

    public PessoaJuridica(String nome, String cnpj, String endereco, String email) {
        super(nome, endereco, email);  // Chama o construtor da classe base puxando o modelo da super classse por isso utiliza o super
        this.cnpj = cnpj;
    }


    String descricao() {
        return super.descricao() + "Cnpj: " + this.cnpj + "\n";
    }
}


class Funcionario extends Pessoa {  // Classe que herda de Pessoa a diferença é que adiciona o cpf e Salario por ser Funcionario
    String cpf;
    double salario;

    public Funcionario(String nome, String cpf, String endereco, double salario) {
        super(nome, endereco, "");  // Não temos email aqui pois não pedido, mas pode ser adicionado caso precise
        this.cpf = cpf;
        this.salario = salario;
    }

   
    String descricao() {
        return super.descricao() + "Cpf: " + this.cpf + "\n" + "Salário: R$ " + this.salario + "\n";
    }
}

public class PessoaFisicaJuridicaFuncionario { // Nesta etapa criei Pessoas fisicas, juridicas e funcionarios com o modelo que foi criado nos retornos acima
    public static void main(String[] args) {
        
        PessoaFisica pf1 = new PessoaFisica("Miguel", "123.456.789-00", "Rua Souza Moraes, 254", "miguel@facens.br");
        PessoaFisica pf2 = new PessoaFisica("João Carlos", "987.654.321-00", "Rua Aparecida, 567", "jc@facens.br");

       
        PessoaJuridica pj1 = new PessoaJuridica("Ricardo", "12.345.678/0001-90", "Prefeitura Sorocaba", "rircado@sorocaba.gov.br");
        PessoaJuridica pj2 = new PessoaJuridica("Diego", "98.765.432/0001-10", "Prefeitura Sorocaba", "diego@sorocaba.gov.br");

        
        Funcionario f1 = new Funcionario("Aiury", "111.222.333-44", "Prefeitura de Sorocaba", 1250.00);
        Funcionario f2 = new Funcionario("Morgana", "444.555.666-77", "Prefeitura de Sorocaba", 3500.00);

      
        System.out.println(pf1.descricao());   // E por ultimo mandei reproduzir as descrições feitas
        System.out.println(pf2.descricao());
        System.out.println(pj1.descricao());
        System.out.println(pj2.descricao());
        System.out.println(f1.descricao());
        System.out.println(f2.descricao());
    }
}



## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

* João Carlos Ferreira de Araujo RA 248152 -- AC2

