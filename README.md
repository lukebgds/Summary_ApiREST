# Api REST e RESTFul

As APIs REST são sistemas que seguem os princípios de arquitetura da REST, permitindo a interação entre sistemas web por meio de interfaces. Essas APIs oferecem uma abordagem uniforme e eficaz para acessar e manipular recursos através de métodos padronizados do protocolo HTTP.

## Diferenças entre REST e RESTFul

REST refere-se aos princípios arquiteturais que norteiam a criação de APIs, enquanto uma API RESTful adere estritamente a esses princípios. Enquanto a REST estabelece diretrizes, a RESTful é uma implementação concreta dessas diretrizes, assegurando a conformidade completa.

### Princípios REST Fundamentais

1. **Interface Uniforme:** Todas as solicitações para o mesmo recurso devem ser iguais, independentemente da origem da solicitação. Isso garante consistência e simplicidade na comunicação.

2. **Desacoplamento do Cliente-Servidor:** O cliente e o servidor devem funcionar de forma independente, permitindo que cada um evolua sem depender diretamente do outro. Isso promove a flexibilidade e a escalabilidade da arquitetura.

3. **Stateless (Sem Estado):** Cada requisição enviada ao servidor deve conter todas as informações necessárias para ser entendida, sem depender de interações anteriores. Isso promove escalabilidade e confiabilidade no sistema.

4. **Cacheável:** As respostas do servidor devem indicar se podem ou não serem armazenadas em cache. Isso melhora a eficiência e a velocidade das interações cliente-servidor.

5. **Sistema em Camadas:** A comunicação entre cliente e servidor ocorre de maneira que nem o cliente nem o servidor saibam se estão se comunicando diretamente entre si ou através de intermediários. Isso proporciona flexibilidade e escalabilidade na arquitetura.

6. **Código sob Demanda (Opcional):** O servidor pode fornecer código executável ao cliente para ampliar sua funcionalidade. Esse recurso é opcional e adiciona flexibilidade à API.

## HTTP verbs

Os métodos HTTP, ou verbos HTTP, indicam a ação a ser realizada em um recurso. Eles são fundamentais para definir as operações que podem ser realizadas em um servidor.

- **GET:** Obtém informações específicas de um recurso.
  
- **HEAD:** Obtém metadados sem o corpo da resposta, útil para verificar a existência de um recurso.
  
- **POST:** Cria um novo recurso no servidor com os dados fornecidos.
  
- **PUT:** Substitui todas as representações atuais do recurso pelo conteúdo da requisição.

- **DELETE:** Remove um recurso específico no servidor.

- **CONNECT:** Estabelece um túnel para o servidor identificado.

- **OPTIONS:** Descreve as opções de comunicação com o recurso.

- **TRACE:** Executa um teste loop-back para o recurso.

- **PATCH:** Aplica modificações parciais a um recurso existente.

# Códigos de Status no HTTP

O elemento Status-Code em uma resposta do servidor é um inteiro de 3 dígitos. O primeiro dígito define a classe da resposta e os dois últimos dígitos não têm nenhum papel de categorização. Existem 5 classes:

- **1xx: Informativo**: Indica que a requisição foi recebida e o processo está em andamento.
- **2xx: Sucesso**: Significa que a ação foi recebida, compreendida e aceita com sucesso.
- **3xx: Redirecionamento**: Implica que uma ação adicional é necessária para completar a requisição.
- **4xx: Erro do Cliente**: Ocorre quando a requisição contém sintaxe incorreta ou não pode ser atendida.
- **5xx: Erro do Servidor**: Surge quando o servidor falha em atender uma requisição aparentemente válida.

Os códigos de status HTTP são extensíveis, e aplicações HTTP não são obrigadas a compreender o significado de todos os códigos de status registrados. Abaixo está uma lista detalhada desses códigos de status:

1. **1xx: Informativo**
   - `100 Continue`: Apenas uma parte do pedido foi recebida e o cliente deve continuar com o pedido.
   - `101 Switching Protocols`: O servidor está mudando de protocolo.

2. **2xx: Sucesso**
   - `200 OK`: O pedido foi bem-sucedido.
   - `201 Created`: O pedido está completo e um novo recurso foi criado.
   - `202 Accepted`: O pedido foi aceito para processamento, mas não concluído.
   - `203 Non-authoritative Information`: A informação é de uma cópia local ou de terceiros.
   - `204 No Content`: A resposta inclui um código de status e cabeçalho, mas sem corpo de entidade.
   - `205 Reset Content`: O navegador deve limpar o formulário usado para essa transação.
   - `206 Partial Content`: O servidor está retornando dados parciais do tamanho solicitado.

3. **3xx: Redirecionamento**
   - `300 Multiple Choices`: O usuário pode selecionar um link de uma lista.
   - `301 Moved Permanently`: A página foi movida permanentemente para um novo URL.
   - `302 Found`: A página foi movida temporariamente para um novo URL.
   - `303 See Other`: A página pode ser encontrada em um URL diferente.
   - `304 Not Modified`: Código de resposta para um cabeçalho If-Modified-Since ou If-None-Match.
   - `305 Use Proxy`: O URL solicitado deve ser acessado através do proxy mencionado no cabeçalho Location.
   - `306 Unused`: Código anteriormente usado, agora reservado.
   - `307 Temporary Redirect`: A página foi movida temporariamente para um novo URL.

4. **4xx: Erro do Cliente**
   - `400 Bad Request`: O servidor não entendeu a requisição.
   - `401 Unauthorized`: A página requisitada precisa de um usuário e senha.
   - `402 Payment Required`: Este código não está em uso.
   - `403 Forbidden`: O acesso à página é proibido.
   - `404 Not Found`: O servidor não conseguiu encontrar a página requisitada.
   - `405 Method Not Allowed`: O método utilizado na requisição não é permitido.
   - `406 Not Acceptable`: O servidor não consegue gerar uma resposta aceitável para o cliente.
   - `407 Proxy Authentication Required`: Autenticação com o proxy é necessária para a requisição ser atendida.
   - `408 Request Timeout`: O servidor excedeu o tempo de espera para a requisição.
   - `409 Conflict`: A requisição não pôde ser completada devido a um conflito com o recurso.
   - `410 Gone`: A página requisitada não está mais disponível.
   - `411 Length Required`: O servidor rejeita a requisição se o tamanho não está especificado.
   - `412 Precondition Failed`: Condição prévia na requisição não foi atendida.
   - `413 Request Entity Too Large`: O servidor não aceita a requisição devido ao tamanho do payload.
   - `414 Request-URI Too Long`: A URI da requisição é muito longa para o servidor processar.
   - `415 Unsupported Media Type`: O formato da requisição não é suportado pelo servidor.
   - `416 Requested Range Not Satisfiable`: O servidor não consegue satisfazer a faixa de bytes requisitada.
   - `417 Expectation Failed`: A expectativa indicada na requisição não pode ser satisfeita pelo servidor.

5. **5xx: Erro do Servidor**
   - `500 Internal Server Error`: O servidor encontrou uma condição inesperada.
   - `501 Not Implemented`: O servidor não suporta a funcionalidade requerida.
   - `502 Bad Gateway`: O servidor recebeu uma resposta inválida do servidor upstream.
   - `503 Service Unavailable`: O servidor está temporariamente sobrecarregado ou indisponível.
   - `504 Gateway Timeout`: O gateway expirou.
   - `505 HTTP Version Not Supported`: O servidor não suporta a versão do protocolo HTTP.

Códigos de status HTTP são essenciais para a comunicação entre clientes e servidores, ajudando a identificar e resolver problemas durante transações HTTP.
---
### **Autor do resumo:** Lucas Benício - 01506393