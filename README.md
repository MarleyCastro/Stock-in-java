
## 🔹 **Bloco 1: Importações e Preparação**

```java
import entities.Product;
import java.util.Locale;
import java.util.Scanner;
```

### Explicação:

* `import entities.Product;`: importa a classe `Product` de outro pacote (provavelmente está em `entities/Product.java`).
* `Locale`: usada para definir o formato de números (ponto em vez de vírgula, por exemplo).
* `Scanner`: usada para ler entradas do usuário.

---

## 🔹 **Bloco 2: Configuração Inicial**

```java
public class Main {
    public static void main(String[] args) {
        Locale.setDefault(Locale.US); // Usa "." como separador decimal
        Scanner sc = new Scanner(System.in); // Prepara o leitor de entradas
```

---

## 🔹 **Bloco 3: Criação do Objeto Produto**

```java
        Product ProdutoA = new Product();
        System.out.format("name: ");
        ProdutoA.name = sc.nextLine();
        System.out.format("Price: ");
        ProdutoA.Price = sc.nextDouble();
        System.out.format("Quantity in stock: ");
        ProdutoA.Quantity = sc.nextInt();
```

### Explicação:

* Um objeto da classe `Product` é criado.
* Os atributos `name`, `Price` e `Quantity` são preenchidos com dados inseridos pelo usuário.

---

## 🔹 **Bloco 4: Exibição dos Dados**

```java
        System.out.println();
        System.out.println("Product data: "+ProdutoA);
```

### Explicação:

* Exibe os dados do produto usando `ProdutoA.toString()`.

---

## 🔹 **Bloco 5: Adicionar Produtos ao Estoque**

```java
        System.out.println();
        System.out.println("Enter the number of productd to be added in stock:" );
        int quantity = sc.nextInt();
        ProdutoA.AddProducts(quantity);
```

### Explicação:

* Usuário informa quantos produtos quer adicionar.
* O método `AddProducts()` atualiza o estoque.

---

## 🔹 **Bloco 6: Mostrar Dados Atualizados**

```java
        System.out.println();
        System.out.println("Updated data: "+ ProdutoA);
```

---

## 🔹 **Bloco 7: Remover Produtos do Estoque**

```java
        System.out.println("Enter the number of productd to be removed in stock:" );
        quantity = sc.nextInt();
        ProdutoA.RemoveProducts(quantity);
```


---

## 🔹 **Bloco 8: Mostrar Dados Finais**

```java
        System.out.println();
        System.out.println("Updated data: "+ ProdutoA);
    }
}
```

---

## 🔹 **Classe `Product`: A Lógica do Produto**

```java
public class Product {
    public String name;
    public double Price;
    public int Quantity;
```

* Atributos públicos: nome, preço e quantidade em estoque.

---

### Métodos da Classe:

```java
    public double totalValueInStock() {
        return Price * Quantity;
    }

    public void AddProducts(int Quantity) {
        this.Quantity += Quantity;
    }

    public void RemoveProducts(int Quantity) {
        this.Quantity -= Quantity;
    }

    public String toString() {
        return name+ ", $ "
                + String.format("%.2f", Price)
                +", "+Quantity
                +" untis, Total: $ "
                +String.format("%.2f",totalValueInStock());
    }
}
```


![image](https://github.com/user-attachments/assets/2530a171-fc6f-4e0e-ac90-4c87723f43ab)
