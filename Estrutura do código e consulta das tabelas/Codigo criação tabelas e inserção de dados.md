 ## SQL  criação das tabelas e inserção de dados nos campos

 ### Comando CREATE  e  INSERT

 ```sql

 1 - Tabela Usuários

 CREATE TABLE Usuarios (
    USUARIO_ID INTEGER PRIMARY KEY,
    NOME_USUARIO VARCHAR(30),
    CPF VARCHAR(30),
    ENDERECO VARCHAR(30),
    TELEFONE VARCHAR(30),
    EMAIL VARCHAR(30)
);


INSERT INTO Usuarios (USUARIO_ID, NOME_USUARIO, CPF, ENDERECO, TELEFONE, EMAIL)
VALUES 
('1', 'Maria Silva', '12345678901', 'Rua A, 123', '11986232021', 'maria@gmail.com'),
('2', 'João Souza', '23456789012', 'Rua C, 456', '11988252630', 'joao@gmail.com'),
('3', 'Katia veloso', '25933152021', 'Rua H, 560', '31978520142', 'ksveloso@gmail.com'),
('4', 'Alice Maria', '44983332090', 'Rua Amilton Silva, 882', '11888888888', 'Amaria@gmail.com'),
('5', 'Sergio Pereira', '59001826067', 'Rua Ana da Ailveira, 600', '35986523120', 'sspereira@gmail.com'),
('6', 'João lima', '34593117038', 'Rua da Acacias, 200', '12988520314', 'joaolima@gmail.com')

```
![Resultado](image-4.png)

**********************************************************************
```sql
2 - Tabela pets

CREATE TABLE Pets (
    PET_ID INTEGER PRIMARY KEY,
    NOME_PET VARCHAR(10),
    PESO VARCHAR(10),
    SEXO VARCHAR(10),
    IDADE VARCHAR(20),
    ESPECIE VARCHAR(15),
    PORTE VARCHAR(15),
    USUARIO_ID INTEGER,
    FOREIGN KEY (USUARIO_ID) REFERENCES Usuarios(USUARIO_ID)
);

INSERT INTO Pets (PET_ID, NOME_PET, PESO, SEXO, IDADE, ESPECIE, PORTE, USUARIO_ID)
VALUES 
(1, 'Rex', '35kg', 'Macho', '4 anos', 'Cachorro', 'Grande', 1),
(2, 'Luna', '7kg', 'Fêmea', '2 anos', 'cachorro', 'Pequeno', 2),
(3, 'pingo', '4kg', 'Macho', '5 meses', 'Gato', 'pequeno', 3),
(4, 'José', '5kg', 'Macho', '2 anos', 'cachorro', 'Pequeno', 5),
(5, 'Beiçola', '3kg', 'Macho', '6 meses', 'Gato', 'Pequeno', 6),
(6, 'Luna', '7kg', 'Fêmea', '2 anos', 'Gato', 'Pequeno', 4)

 ```

![Resultado](image-1.png)
*********************************************************************
```sql
3 - Tabela Localizacao

CREATE TABLE Localizacao (
    LOCALIZACAO_ID INTEGER PRIMARY KEY,
    ENDERECO VARCHAR(30),
    CIDADE VARCHAR(20),
    ESTADO VARCHAR(20),
    PET_ID INTEGER,
    FOREIGN KEY (PET_ID) REFERENCES Pets(PET_ID)
);


INSERT INTO Localizacao (LOCALIZACAO_ID, ENDERECO, CIDADE, ESTADO, PET_ID)
VALUES 
(1, 'Rua A, 123', 'São Paulo', 'SP', 6),
(2, 'Rua B, 456', 'Rio de Janeiro', 'RJ', 2),
(3, 'Rua Martins, 559', 'Salvador', 'BA', 3),
(4, 'Rua Jose da Silva Couto, 56', 'Contagem', 'MG', 5),
(5, 'Rua Bernado Guimaraes, 44', 'Pelotas', 'RS', 4),
(6, 'Rua Alves, 33', 'Olinda', 'PE', 1)

```
![Resultado](image-2.png)

****************************************************************************
```SQL
4- Tabela doacoes

CREATE TABLE Doacoes (
    DOACOES_ID VARCHAR(10) PRIMARY KEY,
    NOME_DOADOR VARCHAR(30),
    VALOR FLOAT,
    FORMA VARCHAR(20),
    DATA VARCHAR(10),
    USUARIO_ID INTEGER,
    FOREIGN KEY (USUARIO_ID) REFERENCES Usuarios(USUARIO_ID)
);

INSERT INTO Doacoes (DOACOES_ID, NOME_DOADOR, VALOR, FORMA, DATA, USUARIO_ID)
VALUES 
('D001', 'João Souza', 200.00, 'Dinheiro', '2024-10-01', 2),
('D002', 'Alice Maria', 150.00, 'Pix', '2024-10-05', 4),
('D003', 'Katia veloso', 150.00, 'Pix', '2024-10-05', 3)

```

![Resultado](image-3.png)