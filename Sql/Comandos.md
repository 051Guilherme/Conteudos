# 📊 Guia de Comandos SQL

---

## 🏗️ 1. Definição de Estrutura (DDL)

### Criando Tabelas
Para criar uma tabela, definimos o nome da coluna, o tipo de dado e suas restrições.

```sql
-- Cria uma tabela de usuários se ela ainda não existir
CREATE TABLE IF NOT EXISTS usuarios (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    idade INT,
    email VARCHAR(50),
    senha VARCHAR(255)
);
```

### Alterando Tabelas (`ALTER TABLE`)
Comandos para modificar a estrutura de uma tabela já existente.

* **Adicionar coluna:** `ALTER TABLE usuarios ADD endereco VARCHAR(100);`
* **Modificar tipo da coluna:** `ALTER TABLE usuarios MODIFY endereco TEXT;`
* **Mudar nome e tipo da coluna:** `ALTER TABLE usuarios CHANGE COLUMN endereco logradouro VARCHAR(255);`
* **Excluir coluna:** `ALTER TABLE usuarios DROP COLUMN idade;`
* **Renomear tabela:** `ALTER TABLE usuarios RENAME TO clientes;`

### Excluindo Tabelas
```sql
DROP TABLE clientes;
```

---

## ✍️ 2. Manipulação de Dados (DML)

### Inserir, Atualizar e Deletar
Operações básicas para gerenciar os registros dentro das tabelas.

```sql
-- Inserir dados
INSERT INTO users (id, username, email, user_password) 
VALUES (1, 'Guilherme','guilherme@gmail.com', 'senha123');

-- Atualizar dados (Sempre use WHERE para não alterar a tabela toda!)
UPDATE users SET email = 'rafaborre@gmail.com' WHERE id = 2;

-- Deletar dados
DELETE FROM users WHERE id = 2;
```

---

## 🔍 3. Consultas e Filtros (DQL)

### Consultas Básicas
```sql
-- Selecionar tudo
SELECT * FROM produtos;

-- Ordenação (ASC para crescente, DESC para decrescente)
SELECT * FROM guerreiros ORDER BY poder_de_luta ASC;

-- Filtros com condições
SELECT * FROM guerreiros WHERE poder_de_luta > 9000 ORDER BY nome ASC;

-- Limitar resultados e buscar valores únicos
SELECT * FROM guerreiros LIMIT 3;
SELECT DISTINCT universo FROM guerreiros;
```

### Funções de Agregação
Utilizadas para realizar cálculos matemáticos nos conjuntos de dados.

| Função | Descrição |
| :--- | :--- |
| `SUM(coluna)` | Soma todos os valores. |
| `AVG(coluna)` | Calcula a média. |
| `MAX(coluna)` | Retorna o maior valor. |
| `MIN(coluna)` | Retorna o menor valor. |

---

## 🔗 4. Relacionamentos e Joins

### Chaves Estrangeiras (FK) com Cascade
O uso de `ON DELETE CASCADE` garante que, se um registro pai for deletado, os registros filhos vinculados também serão removidos.

```sql
CREATE TABLE pedidos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT,
    data_pedido DATE,
    CONSTRAINT fk_cliente
        FOREIGN KEY (cliente_id) REFERENCES clientes(id)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);
```

### Junção de Tabelas (`JOIN`)
Permite consultar dados que estão espalhados em múltiplas tabelas relacionadas.

```sql
-- Inner Join: Retorna apenas registros com correspondência em ambas as tabelas
SELECT u.nome, p.id_produtos, pr.nome
FROM usuarios u
INNER JOIN pedidos p ON u.id = p.id_usuarios
INNER JOIN produtos pr ON p.id_produtos = pr.id;

-- Left Join: Retorna todos os usuários, mesmo os que não possuem pedidos
SELECT u.nome, p.id
FROM usuarios u
LEFT JOIN pedidos p ON u.id = p.id_usuarios;
```

---

## 📚 5. Estudo de Caso: Sistema de Livraria

Abaixo, exemplos de consultas avançadas aplicadas ao cenário de uma livraria (Clientes, Livros e Pedidos).

### Relatórios Úteis

* **Total de vendas por livro:**
    ```sql
    SELECT l.titulo, SUM(ip.quantidade) AS total_vendido
    FROM itens_pedidos ip
    JOIN livros l ON ip.livro_id = l.id
    GROUP BY l.titulo;
    ```

* **Valor total de cada pedido:**
    ```sql
    SELECT p.id AS pedido_id, SUM(l.preco * ip.quantidade) AS valor_total
    FROM pedidos p
    JOIN itens_pedidos ip ON p.id = ip.pedido_id
    JOIN livros l ON ip.livro_id = l.id
    GROUP BY p.id;
    ```

* **Ranking de clientes que mais compraram:**
    ```sql
    SELECT c.nome, SUM(ip.quantidade) AS total_livros
    FROM clientes c
    JOIN pedidos p ON c.id = p.cliente_id
    JOIN itens_pedidos ip ON p.id = ip.pedido_id
    GROUP BY c.nome
    ORDER BY total_livros DESC;
    ```

* **Vendas por mês:**
    ```sql
    SELECT DATE_FORMAT(data_pedido, '%Y-%m') AS ano_mes, COUNT(*) AS total_pedidos
    FROM pedidos
    GROUP BY ano_mes;
    ```

---

> **Dica:** Ao realizar `UPDATE` ou `DELETE`, certifique-se de que a cláusula `WHERE` está correta para evitar a perda acidental de dados! ⚠️