1) No seu github pessoal, criar um repositório de banco de dados (caso ainda não exista) e dentro dele um arquivo chamado vocabulario.md. Nele preencher o significado das expressões abaixo, mantendo o texto ordenado:
	
  - sistema gerenciador de banco de dados
    -  Sistema de Gerenciamento de Banco de Dados (SGBD) é um conjunto de software utilizado para o gerenciamento de uma base de dados, responsáveis por controlar, acessar, organizar e proteger as informações de uma aplicação.

  - restrições em banco de dados
    - há cinco tipos de restrições: funcional. integridade, estrutural, referemcial e NOT NULL.
    
	- modelo relacional
    - É um modelo de dados usado em SGBDs que organiza os dados em tabelas ou relações.

	- modelagem conceitual
    - É uma fase no processo de desenvolvimento de sistemas onde se foca na representação dos requisitos e das entidades principais do sistema, concentrando-se em capturar as principais entidades, relacionamentos e atributos de um domínio de negócio de uma forma abstrata e de alto nível.

	- modelagem lógica
    - É uma etapa intermediária no processo de desenvolvimento onde, o foco está na representação detalhada e estruturada dos dados do sistema, sem considerar ainda a implementação física específica em um determinado SGBD.

	- modelagem física
    - É a fase do processo de desenvolvimento onde o foco está na implementação concreta e específica da estrutura de dados em um SGBD.

	- linguagem SQL
    - Structured Query Language, ou SQL, é uma linguagem padrão usada para acessar e manipular bancos de dados relacionais.

	- Data Definition Language (DDL)
    - É uma parte da linguagem SQL que permite aos usuários definir e gerenciar estruturas de banco de dados. Ela é usada para descrever e especificar como os dados devem ser armazenados e organizados em um banco de dados.
    
	- Data Manipulation Language (DML)
    - É uma parte da linguagem SQL que permite aos usuários acessar e manipular os dados armazenados em um banco de dados relacional. A DML é utilizada para realizar operações de consulta, inserção, atualização e exclusão de dados dentro das tabelas do banco de dados.
    
	- Boas práticas em modelagem de banco de dados
    - Aplicar técnicas de normalização para evitar redundância de dados, definir chaves primárias para cada tabela, utilizar chaves estrangeiras para estabelecer relacionamentos entre tabelas, documentar adequadamente a estrutura do banco de dados, monitorar o desempenho do banco de dados regularmente e otimizar consultas, índices e estruturas conforme necessário para garantir um desempenho eficiente.


2) Por meio do MySQL Workbench OU MS Studio Managament faça o seguinte esquema de banco e responda as questões.

   Todos os clientes armazenados no sistema:
SELECT * FROM cliente;

- Exiba os veículos que tenham final 3 no número da placa
SELECT * FROM veiculo WHERE placa LIKE '%3';

- Mostre os clientes que residem no RS e que não possuam telefone
SELECT * FROM cliente WHERE uf_cnh = 'RS' AND telefone IS NULL;

- Quantos veículos há cadastrados no sistema
SELECT COUNT(*) AS  total_veiculos FROM veiculo;

- Mostre o veículo alugado por Alexandre Zamberlan.
SELECT v.* FROM cliente c JOIN contrato_aluguel ca ON c.id_cliente = ca.id_cliente JOIN veiculo v ON ca.id_veiculo = v.id_veiculo WHERE c.nome = 'Alexandre Zamberlan';

- Mostre os clientes e os escritórios associados no contrato de aluguel.
SELECT c.nome as nome_cliente, e.nome as nome_escritorio FROM contrato_aluguel ca JOIN cliente c ON ca.id_cliente = c.id_cliente JOIN escritorio e ON ca.id_escritorio = e.id_escritorio;
