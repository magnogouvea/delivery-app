# Boas-vindas ao repositório do Projeto App de Delivery

Para abrir o projeto, atente-se as orientações descritas a seguir, e, caso tenha qualquer dúvida, entre em contato.

<summary><strong>👨‍💻 Projeto App de Delivery</strong></summary><br  />

Essa aplicação integra tanto o back-end quanto o front-end, criando uma plataforma de delivery de bebidas. 🍻
 
Projeto desenvolvido em grupo com pessoas excelentes e maravilhosas.
 
 #### Contexto do projeto:
 
A distribuidora de cervejas da dona Tereza está se informatizando! 🚀 Seu negócio, antes focado em um local específico da cidade, passou a receber uma quantidade massiva de encomendas de outros pontos, expandindo sua atuação via delivery. Isso tudo graças ao excelente preço das bebidas e atendimento da equipe de vendas.
 

Agora a distribuidora possui alguns pontos de venda na cidade para agilizar no atendimento dessas áreas. Cada ponto de venda, por sua vez, possui uma pessoa vendedora responsável.
  

Como seu antigo sistema, que era um conjunto de planilhas, já não atende a necessidade do negócio por gerar muita manutenção, dona Tereza procurou uma equipe de pessoas desenvolvedoras com uma ideia de aplicativo que pudesse agilizar a vida de sua equipe e das pessoas que compram seus produtos. O aplicativo precisa:
  

- Ter acesso via login: tanto clientes como pessoas vendedoras, assim como a própria dona Tereza, que administra o sistema, devem ter acesso ao aplicativo via login, porém para funções diferentes: (1) A pessoa cliente, que compra da lista de produtos; (2) A pessoa vendedora, que aprova, prepara e entrega; (3) A pessoa administradora, que gerencia quem usa o aplicativo;

- Fazer a comunicação entre clientes e pessoas vendedoras: a pessoa cliente faz o pedido via "carrinho de compras" e a pessoa vendedora aprova, prepara e envia esse pedido. Quando o produto é recebido por quem comprou, essa pessoa marca o pedido como "recebido". Ambos devem possuir detalhes sobre seus pedidos;

- Se a pessoa cliente faz o pedido, o mesmo deve aparecer para a pessoa vendedora em seu dash de pedidos após a atualização da página. A pessoa cliente, por sua vez, deve ter as informações sobre seu pedido quando sua página for atualizada, ou seja, ter informações se o pedido está sendo preparado ou se já saiu pra entrega;

A equipe criou o [Diagrama de ER](./eer.png) para criar o banco de dados, conforme imagem: 

![Diagrama de ER](./eer.png)

<!--
<strong>🚵 Habilidades trabalhadas:</strong>

<ul>
<li>Lógica</li>
<li>Capacidade de interpretação de problemas</li>
<li>Capacidade de otimizar a resolução de problemas</li>
<li>Resolver problemas/Otimizar algoritmos sob pressão.</li>
</ul>

-->

</details>


# Orientações

<details>

<summary><strong>⚠ Como iniciar o projeto</strong></summary><br  />

  
<!--

1. Clone o repositório

  

- Use o comando: `git clone git@github.com:AntunesGean/algorithms.git`

- Entre na pasta do repositório que você acabou de clonar:

-  `cd algorithms`

  

2. Crie o ambiente virtual para o projeto

  

-  `python3 -m venv .venv && source .venv/bin/activate`

3. Instale as dependências

  

-  `python3 -m pip install -r dev-requirements.txt`

4. E está pronto para usar e testar!

-->

1. Clone o repositório

  

- Use o comando: `git clone git@github.com:AntunesGean/delivery-app.git`.

- Entre na pasta do repositório que você acabou de clonar:

-  `cd delivery-app`


2. Instale as dependências
  
- Para isso, use o seguinte comando: `npm install`

3. E está pronto para usar e testar!

</details>

<details><summary>
<strong>🪛 Scripts relevantes do <code>package.json</code> principal</strong>
</summary><br>

  

**Observação:** nesse projeto, utilizamos o gerenciador de processos `pm2`. Caso você queira entender melhor o que são gerenciadores de processos Node, dê uma conferida [nesse link](https://app.betrybe.com/learn/course/5e938f69-6e32-43b3-9685-c936530fd326/module/f04cdb21-382e-4588-8950-3b1a29afd2dd/section/c2647acd-7619-4c8a-a7d8-13b452281c35/lesson/99c92a3a-8b45-4428-8ed6-c1c8a7ffdeac).

  

**São os scripts da raiz do projeto (`./package.json`) e não das aplicações individuais `./front-end/package.json` e `./back-end/package.json`**:

  

-  `start`: Limpa as portas `3000` e `3001` e simula a inicialização no avaliador. Também prepara o campo rodando o `Sequelize` para restaurar o **banco de dados de testes** (final `-test`) e sobe a aplicação com `pm2` em modo `fork` (uma instância para cada aplicação). Nesse modo, as alterações não são assistidas;

-  *uso (na raiz do projeto): `npm start`*

  

-  `stop`: Para e deleta as aplicações rodando no `pm2`;

-  *uso (na raiz do projeto): `npm stop`*

  

-  `dev`: Limpa as portas `3000` e `3001` e sobe a aplicação com `pm2` em modo `fork` (uma instância pra cada aplicação). Nesse modo, as atualizações são assistidas (modo `watch`);

-  *uso (na raiz do projeto): `npm run dev`*

  

-  `dev:prestart`: A partir da raiz, esse comando faz o processo de instalação de dependências (`npm i`) nos dois projetos (`./front-end` e `./back-end`) e roda o `Sequelize` no `./back-end` (lembrar de configurar o `.env` no mesmo);

-  *uso (na raiz do projeto): `npm run dev:prestart`*

  

-  `db:reset`: Roda os scripts do `Sequelize` restaurando o **banco de dados de desenvolvimento** (final `-dev`). Utilize esse script caso ocorra algum problema no seu banco local;

-  *uso (na raiz do projeto): `npm run db:reset`*

  

-  `db:reset:debug`: Roda os scripts do `Sequelize` restaurando o **banco de dados de desenvolvimento** (final `-dev`). Utilize esse script caso ocorra algum problema no seu banco local. Esse comando também é capaz de retornar informações detalhadas de erros (quando ocorrerem no processo);

-  *uso (na raiz do projeto): `npm run db:reset:debug`*

  

-  `test <nomes-dos-arquivos>`: Roda todos os testes (ou uma parte deles caso `<nomes-dos-arquivos>` seja definido) utilizando o **banco de dados de testes** (final `-test`);

-  *uso (na raiz do projeto): `npm test`, `npm test 01login 02register` ou ainda `npm run test 01 02`*

  

-  `test:dev <nomes-dos-arquivos>`: Roda todos os testes (ou uma parte deles caso `<nomes-dos-arquivos>` seja definido) utilizando o **banco de dados de desenvolvimento** (final `-dev`);

-  *uso (na raiz do projeto): `npm run test:dev`, `npm run test:dev 01login 02register` ou ainda `npm test:dev 01 02`*;

  

-  `test:dev:open <nomes-dos-arquivos>`: Roda todos os testes (ou uma parte deles caso `<nomes-dos-arquivos>` seja definido) utilizando o **banco de dados de desenvolvimento** (final `-dev`), exemplo `npm test:dev:open 01login 02register` ou ainda `npm test:dev:open 01 02`. Esse teste deve abrir uma janela mostrando o comportamento das páginas;

-  *uso (na raiz do projeto): `npm run test:dev:open`, `npm run test:dev:open 01login 02register` ou ainda `npm test:dev:open 01 02`*;

  

-  `test:dev:report "<nomes-dos-arquivos>"`: Roda todos os testes (ou uma parte deles caso `"<nomes-dos-arquivos>"` seja definido) utilizando o **banco de dados de desenvolvimento** (final `-dev`). Esse teste devolve um output em texto com o resultado de todos os testes. Os `logs` são gerados em `./__tests__/reports`.

-  *uso (na raiz do projeto): `npm run test:dev:report`, `npm run test:dev:report "01login 02register"` ou ainda `npm run test:dev:report "01 02"`*;


</details>
