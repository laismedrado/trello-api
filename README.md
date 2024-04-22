# TRELLO - API
Este repositório contém testes de API para os endpoints de ações do Trello, os quais foram realizados utilizando o Postman. Eles incluem interações com as ações mais importantes que os usuários executam em um quadro do Trello. A automação desses testes via GitHub Actions foi implementada devido à relevância dessas ações para os usuários.

## Tecnologias utilizadas
- Postman versão web
- node version v18.16.1
- newman v5.3.2
- newman-reporter-html
  
## Documentações
 [Documentação da API do Trello](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)
 
## Como instalar o ambiente
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
## Como rodar os testes
### Pelo Postman web ou desktop
- Import a collection e o environment
- Execute os teste de forma manual ou automatizada
### Pelo newman
- Abra o console de preferência
- Execute a seguinte linha de comando para rodar os testes
```
newman run Trello.postman_collection.json -r cli
```
- Execute os teste com relatório
```
newman run Trello.postman_collection.json -r cli,htmlextra
```
### Report
Se você optou por rodar os teste com o report htmlextra, você gerou um arquivo html com o resultado dos testes e para verificar as validações você pode abrir a pasta newman que foi criada no local em que os arquivos da collection e environment se encontram;

## Entre em contato
email: laismedrado@live.com
redes socias: https://www.linkedin.com/in/lais-medrado/



# trello-api
Trello API test in Postman for interacting with actions on a Trello board, ensuring functionality and integrity. Executed in a pipeline on GitHub Actions.
