
# Aprenda Bancos de Dados Relacionais Criando um Banco de Dados do Mario

## Acessando e Gerenciando o Banco de Dados

1. **Entrar no PostgreSQL:**
   ```sql
   psql --username=freecodecamp --dbname=postgres
   ```

2. **Listar bancos de dados existentes:**
   ```sql
   \l
   ```

3. **Criar um novo banco de dados:**
   ```sql
   CREATE DATABASE nome_do_banco;
   ```

4. **Conectar-se a um banco de dados:**
   ```sql
   \c nome_do_banco
   ```

## Trabalhando com Tabelas

1. **Listar tabelas existentes:**
   ```sql
   \d
   ```

2. **Criar uma nova tabela:**
   ```sql
   CREATE TABLE nome_da_tabela();
   ```

3. **Visualizar detalhes de uma tabela específica:**
   ```sql
   \d nome_da_tabela
   ```

4. **Adicionar uma coluna em uma tabela:**
   ```sql
   ALTER TABLE nome_da_tabela ADD COLUMN nome_da_coluna TIPO_DE_DADO;
   ```

5. **Remover uma coluna:**
   ```sql
   ALTER TABLE nome_da_tabela DROP COLUMN nome_da_coluna;
   ```

6. **Renomear uma coluna:**
   ```sql
   ALTER TABLE nome_da_tabela RENAME COLUMN nome_antigo TO novo_nome;
   ```

## Gerenciamento de Dados

1. **Inserir uma linha na tabela:**
   ```sql
   INSERT INTO nome_da_tabela(coluna_1, coluna_2) VALUES(valor1, valor2);
   ```

2. **Inserir múltiplas linhas de uma só vez:**
   ```sql
   INSERT INTO personagens(nome, reino, cor_favorita)
   VALUES ('Mario', 'Reino dos Cogumelos', 'Vermelho'),
          ('Luigi', 'Reino dos Cogumelos', 'Verde'),
          ('Peach', 'Reino dos Cogumelos', 'Rosa');
   ```

3. **Visualizar os dados de uma tabela:**
   ```sql
   SELECT colunas FROM nome_da_tabela;
   ```

4. **Atualizar valores em uma tabela:**
   ```sql
   UPDATE nome_da_tabela SET nome_da_coluna = novo_valor WHERE condicao;
   ```

5. **Ordenar resultados de uma consulta:**
   ```sql
   SELECT colunas FROM nome_da_tabela ORDER BY nome_da_coluna;
   ```

6. **Deletar uma linha:**
   ```sql
   DELETE FROM nome_da_tabela WHERE condicao;
   ```

7. **Deletar uma tabela:**
   ```sql
   DROP TABLE nome_da_tabela;
   ```

## Gerenciamento de Chaves e Restrições

1. **Definir uma chave primária:**
   ```sql
   ALTER TABLE nome_da_tabela ADD PRIMARY KEY(nome_da_coluna);
   ```

2. **Remover uma restrição:**
   ```sql
   ALTER TABLE nome_da_tabela DROP CONSTRAINT nome_da_restricao;
   ```

3. **Adicionar uma chave estrangeira:**
   ```sql
   ALTER TABLE nome_da_tabela ADD COLUMN nome_da_coluna TIPO_DE_DADO REFERENCES tabela_referenciada(coluna_referenciada);
   ```

4. **Adicionar uma chave estrangeira a uma coluna existente:**
   ```sql
   ALTER TABLE nome_da_tabela ADD FOREIGN KEY(nome_da_coluna) REFERENCES tabela_referenciada(coluna_referenciada);
   ```

5. **Criar uma chave primária composta:**
   ```sql
   ALTER TABLE nome_da_tabela ADD PRIMARY KEY(coluna1, coluna2);
   ```

## Trabalhando com Relacionamentos

1. **Relacionamento "um-para-um":**
   - Use a restrição `UNIQUE` para garantir exclusividade em uma coluna.
   ```sql
   ALTER TABLE nome_da_tabela ADD UNIQUE(nome_da_coluna);
   ```

2. **Relacionamento "um-para-muitos":**
   - Exemplo de adição de chave estrangeira:
   ```sql
   ALTER TABLE nome_da_tabela ADD COLUMN nome_da_coluna TIPO_DE_DADO REFERENCES tabela_referenciada(coluna_referenciada);
   ```

3. **Realizar junções (`JOIN`) entre tabelas:**
   - Junção de duas tabelas:
   ```sql
   SELECT colunas FROM tabela_1 
   FULL JOIN tabela_2 ON tabela_1.chave_primaria = tabela_2.chave_estrangeira;
   ```

   - Junção de três tabelas:
   ```sql
   SELECT colunas FROM tabela_intermediaria
   FULL JOIN tabela_1 ON tabela_intermediaria.chave_estrangeira_1 = tabela_1.chave_primaria
   FULL JOIN tabela_2 ON tabela_intermediaria.chave_estrangeira_2 = tabela_2.chave_primaria;
   ```
