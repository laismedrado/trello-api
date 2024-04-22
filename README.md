# TRELLO - API
Este repositório contém testes de API para os endpoints de ações do Trello, os quais foram realizados utilizando o Postman. Eles incluem interações com as ações mais importantes que os usuários executam em um quadro do Trello. A automação desses testes via GitHub Actions foi implementada pensando na relevância dessas ações para os usuários.

## Tecnologias utilizadas:
- Postman versão web
- node version v18.16.1
- newman v5.3.2
- newman-reporter-html
  
## Documentações:
 [Documentação da API do Trello](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)
 
## Como instalar o ambiente:
- Primeiro: instale o node em seu computador [baixe aqui](https://nodejs.org/en/download)
- Segundo: realize a instalação do newman de forma global [baixe aqui a dependencia](https://www.npmjs.com/package/newman)
```
npm install -g newman
```
- Terceiro: realize a instalação da dependencia dos relatórios (opcional) [newman-reporter-html
](https://www.npmjs.com/package/newman-reporter-html)
```
npm install -g newman-reporter-html
```
## Como rodar os testes:
### Pelo Postman web ou desktop
- Import a collection e o environment
- Execute os teste de forma manual ou automatizada
### Pelo newman:
- Abra o console de preferência
- Execute a seguinte linha de comando para rodar os testes
```
newman run Trello.postman_collection.json -r cli
```
- Execute os teste com relatório
```
newman run Trello.postman_collection.json -r cli,htmlextra
```
## Report:
Se você optou por rodar os teste com o report htmlextra, você gerou um arquivo html com o resultado dos testes e para verificar as validações você pode abrir a pasta newman que foi criada no local em que os arquivos da collection e environment se encontram;

## Os testes:
Os testes aplicados fazem a seguinte verificação nos endpoints:

    Get All boards:
    - Verifica se a requisição retorna um código de status 200.
    - Extrai o ID do primeiro quadro retornado na resposta e o armazena em variáveis de coleção.
    
    Get single board:
    - Verifica se a requisição retorna um código de status 200.
    - Extrai o ID do quadro retornado na resposta e o armazena em variáveis de coleção.
    
    Create todo list:
    - Verifica se a requisição retorna um código de status 200.
    - Verifica se uma lista de "TODO" é criada com sucesso no quadro selecionado.
    - Armazena o ID da lista "TODO" criada em variáveis de coleção.
    
    Create done list:
    - Verifica se a requisição retorna um código de status 200.
    - Verifica se uma lista de "DONE" é criada com sucesso no quadro selecionado.
    - Armazena o ID da lista "DONE" criada em variáveis de coleção.
    
    Create a new Card:
    - Verifica se a requisição retorna um código de status 200.
    - Verifica se um cartão é criado com sucesso na lista "TODO" do quadro selecionado.
    - Armazena o ID do cartão criado em variáveis de coleção.
    
    Create board:
    - Verifica se a requisição retorna um código de status 200.
    - Verifica se um novo quadro é criado com sucesso.
    - Verifica se o quadro criado é privado e se o calendário está desativado.
    - Incrementa um número de identificação do quadro para garantir a exclusividade do nome.
    
    Move card to done list:
    - Verifica se a requisição retorna um código de status 200.
    - Verifica se o cartão é movido com sucesso para a lista "DONE" do quadro.
    
    Delete board:
    - Remove um quadro existente.
    - Verifica se a requisição retorna um código de status 200.
    
    Get deleted board:
    - Verifica se uma tentativa de acessar um quadro excluído retorna um código de status 404.

## Lógica:

Lógica utilizada nos testes:

- Captura de resultados: Cada teste captura informações relevantes dos resultados das requisições, como IDs de quadros, listas e cartões, utilizando a função `pm.response.json()` para analisar o corpo da resposta.
- Armazenamento em variáveis: As informações capturadas são armazenadas em variáveis de coleção utilizando o método `pm.collectionVariables.set()`. Isso permite que esses dados sejam acessados e utilizados em outros testes dentro da mesma coleção.
- Reutilização de variáveis: As variáveis armazenadas são reutilizadas em testes subsequentes para compor as URLs das requisições e verificar se o comportamento esperado dos endpoints está sendo alcançado. Isso simplifica a escrita dos testes e evita a repetição de código, garantindo a consistência e a manutenibilidade dos scripts de teste.

## Contato:

Se você tiver alguma dúvida, sugestão ou encontrar algum problema nos testes ou na documentação, sinta-se à vontade para entrar em contato.
email: laismedrado@live.com
redes socias: [Linkedin](https://www.linkedin.com/in/lais-medrado/)
