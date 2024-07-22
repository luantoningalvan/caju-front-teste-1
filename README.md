# Caju Front End Teste

Olá, seja muito bem-vindo(a) a minha resolução do teste para front-end da Caju.

## Como executar o projeto

- O projeto pode ser acessado no navegador através do link: [https://caju-ten.vercel.app](https://caju-ten.vercel.app)
- Para executar localmente:
  - Clone o repositório
  - Instale as dependências com `yarn install`
  - Execute o servidor mock com `yarn db:init`
  - Execute o projeto com `yarn dev`
  - Se tudo ocorrer bem o projeto estará rodando em [http://localhost:3001](http://localhost:3001)
- Para a execução dos testes, existem diferentes cenários
  - Caso deseje executar somente os testes unitários, execute `yarn test:jest`
  - Caso deseje executar somente os testes de integração/e2e, certifique-se que as portas 3000 e 3001 estão livres e execute `yarn test:cy`
  - Para executar todos os testes em conjunto e gerar um coverage unificado, execute `yarn test`

## Apresentanção do problema

O desafio é melhorar a organização do projeto, refatorar o código e implementar algumas regras e novas funcionalidades(logo abaixo).
Sinta-se a vontade para criar novas pastas, novos utils, contextos, custom hooks, o que achar melhor para deixar o projeto mais organizado e atigir as especificações abaixo.

## Especificações

### Dashboard

- Implementar `GET` ao carregar a pagina e ao fazer pequisa por `CPF`
- Filtrar os cards por coluna, usando o status.
- Implementar `PUT` ao clicar em Reprovar e alterar o status para `REPROVED`
- Implementar `PUT` ao clicar em Aprovar e alterar o status para `APPROVED`
- Implementar `PUT` ao clicar em Revisar novamente e alterar o status para `REVIEW`
- Implementar `DELETE` ao clicar no lixeira no card.
- Implementar um loading na tela ao realizar requisições.
- Realizar a requisição automaticamente ao preencher um CPF válido completo
- Atualizar os dados (refetch) ao clicar no icone de atualizar
- Adicionar máscara de CPF no campo de pesquisa.

### Pesquisa por CPF

Para realizar a pesquisa por CPF, utilize essa funcionalidade do json-web-server:
<br/>
https://github.com/typicode/json-server/tree/v0?tab=readme-ov-file#filter

### Formulário

- Implementar validação no campo de `email` para que aceite apenas emails válidos
- Implementar validação no campo `nome completo` para que aceite pelo menos um espaço, no mínimo duas letras, e que a primeira letra não seja um número.
- Implementar validação no campo CPF para aceitar apenas CPFs válidos e adicionar uma máscara de CPF ao campo.
- Implementar `POST` ao preencher todos os campos corretamentes.
- Redirecionar ao `/dashboard` ao criar uma nova registration.

## Regras de negócio

- Implementar tipagem correta e enums em TypeScript.
- Todas as requisições devem ter modal de confirmação da ação
- Todas as requisições devem aparecer uma notificação de sucesso ou erro
- O botão de `Reprovar` e `Aprovar` só deve aparecer em registrations com status `REVIEW`
- O botão `Revisar novamente` só deve aparecer em registration com status `REPROVED` ou `APPROVED`

## API

Você consumirá uma API mockada localmente, que será executada utilizando o json-server. Para mais informações consulte a [documentação](https://github.com/typicode/json-server/).

Exemplo de Requisição:

```
POST http://localhost:3000/registrations
Content-Type: application/json
{
  "admissionDate": "23/10/2023",
  "email": "maria@caju.com.br",
  "employeeName": "Maria Silva",
  "status": "REVIEW",
  "cpf": "12345678901"
}
```

## Extras (opcional)

- Testes Unitários e de Integração `(Obrigátorio para Senior e Tech Lead)`
- End-to-End (E2E)
- Documentação detalhada utilizando Storybook e Docusaurus
- Configuração de CI/CD com deploy automatizado

## Dicas e sugestões

- Crie custom hooks para separar a lógica da camada de UI.
- Utilize alguma lib de validação para o formulário
- Crie testes que simulem o comportamento esperado do usuario.
