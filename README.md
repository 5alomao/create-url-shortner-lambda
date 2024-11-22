# Create URL Shortner Lambda

## Descrição do Projeto

Este projeto implementa uma função **AWS Lambda** que atua como um encurtador de URLs. Ele recebe uma requisição `POST` 
centralizada por meio de um **API Gateway**, parseia e extrai os dados enviados no corpo da requisição. 
Em seguida, cria um arquivo JSON contendo a URL original e a data de expiração fornecida. Esse arquivo é salvo em um bucket no **Amazon S3**, 
com um **UUID** gerado automaticamente como nome do arquivo.  
  
## Endpoints

## `POST /create`

**Descrição**: Salva o arquivo JSON no Amazon S3, que contém a URL original e a data de expiração.

**Corpo da Requisição**:
```json
{
	"originalUrl": "https://github.com/5alomao",
	"expirationTime": "1763933886000"
}
```
### Resposta
- **200: OK** caso a operação seja feita com sucesso.

## Funcionamento

- A função Lambda é acionada ao receber uma requisição POST no endpoint configurado.
- A requisição é processada para extrair os dados de originalUrl e expirationTime.
- Um UUID é gerado para ser o nome único do arquivo JSON.
- O arquivo JSON é criado e enviado para o Amazon S3 em um bucket especificado.
- Retorna uma resposta indicando o sucesso ou falha da operação.

## Tecnologias Utilizadas

- AWS Lambda: Para processar as requisições.
- Amazon S3: Para armazenar os arquivos JSON.
- Java (versão 17)
- Insomnia: Para testar as requisições
- UUID: Para geração de identificadores únicos.
