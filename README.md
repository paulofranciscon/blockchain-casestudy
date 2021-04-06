# Resumo

Este repositório foi elaborado e documentado para orientar a preparação do ambiente de execução da aplicação que simula as funcionalidades de uma rede Blockchain.


# Parte 1 - Blockchain

1- Use o NPM para inicializar seu projeto e criar o arquivo package.json para armazenar as dependências do projeto.

npm init


2- Instale o crypto-js com o sinalizador --save para salvar a dependência em nosso arquivo package.json

npm install crypto-js --save


3- Instale o pacote do levelDB com a flag --save

npm install level --save



# Parte 2 - App Web

Execute: 

npm install fs
npm install express
npm install body-parser



# Estrutura do Projeto

blockchainDatabase.js

Contém a classe leveldb, isso permite que os blocos na cadeia sejam persistentes. As funções dentro da classe são assíncronas, significando que múltiplas operações podem ocorrer de uma só vez. Operações assíncronas são feitas através de Promises que devem ser tratadas apropriadamente.


app.js

Consiste em duas classes, Block class e Blockchain class. Juntas criam uma blockchain privada funcional. Com a ajuda do blockchainDatabase, a cadeia de blocos pode ser salva e reutilizada.

A classe de bloco consiste em apenas um construtor que descreve o objeto de bloco (hash, height, corpo, hora, previousBlockHash).

A classe BlockChain contém funções assíncronas que lidam com a criação da cadeia e o gerenciamento de blocos na cadeia. O motivo pelo qual as funções Blockchain retornam Promise permite que os dados do leveldb sejam usados ​​sem ter variáveis ​​desconhecidas.

Esse arquivo contém as funções da app web que aceita receber e postar solicitação do navegador do cliente para gerenciar e visualizar a blockchain. Cada solicitação get e post chama a função blockChain correspondente com variáveis ​​passadas do cliente. Ele utiliza o operador de espera para receber o Promise que será enviado de volta ao cliente.


privateblockchain.html

Código html e javascript dinâmico para melhor visualizar e gerenciar a cadeia de blocos privados.


chaindata

Onde os dados da blockchain são armazenados. Se um bloco for alterado ou uma nova cadeia for necessária, a pasta chaindata poderá ser excluída.






