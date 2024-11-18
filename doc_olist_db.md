# Documentação do Banco de Dados `olist_db`

<br>

<img src="https://github.com/enzodelcompare/treinamento-sql-olist/blob/main/imagens/olista_db.png">

<br>

## Descrição Geral

O banco de dados `olist_db` foi projetado para armazenar informações relacionadas ao comércio eletrônico, utilizando o conjunto de dados público da **Olist**. Ele é composto por várias tabelas que representam diferentes entidades e operações do negócio, como clientes, vendedores, produtos, pedidos, geolocalização, pagamentos e avaliações. O design segue os princípios de um modelo relacional, garantindo integridade e consistência dos dados.

<br>

## Estrutura das Tabelas

### 1. Tabela clientes

Armazena informações básicas dos clientes.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_cliente`|**VARCHAR(255)**|Identificador único do cliente (chave primária).|
|`id_cliente_unico`|**VARCHAR(255)**|ID único para identificar clientes recorrentes (único e obrigatório).|
|`prefixo_cep_cliente`|**INT**|Prefixo do CEP do cliente.|
|`cidade_cliente`|**VARCHAR(100)**|Nome da cidade do cliente.|
|`estado_cliente`|CHAR(2)**|Sigla do estado do cliente.|

**Relacionamentos:**

**Chave estrangeira:** `prefixo_cep_cliente` -> `geolocalizacao(prefixo_cep)`.

<br>

### 2. Tabela vendedores

Armazena informações sobre os vendedores.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_vendedor`|**VARCHAR(255)**|Identificador único do vendedor (chave primária).|
|`prefixo_cep_vendedor`|**INT**|Prefixo do CEP do vendedor.|
|`cidade_vendedor`|**VARCHAR(100)**|Nome da cidade do vendedor.|
|`estado_vendedor`|**CHAR(2)**|Sigla do estado do vendedor.|

**Relacionamentos:**

**Chave estrangeira:** `prefixo_cep_vendedor` -> `geolocalizacao(prefixo_cep)`.

<br>

### 3. Tabela geolocalizacao

Armazena informações de localização geográfica baseadas no prefixo do CEP.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`prefixo_cep`|**INT**|Prefixo do CEP (chave primária).|
|`latitude`|**DECIMAL(10, 8)**|Latitude associada ao CEP.|
|`longitude`|**DECIMAL(11, 8)**|Longitude associada ao CEP.|
|`cidade`|**VARCHAR(100**)|Nome da cidade associada ao CEP.|
|`estado`|**CHAR(2)**|Sigla do estado associado ao CEP.|

<br>

### 4. Tabela produtos

Armazena informações sobre os produtos disponíveis.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_produto`|**VARCHAR(255)**|Identificador único do produto (chave primária).|
|`categoria_produto`|**VARCHAR(100)**|Categoria do produto.|
|`peso_produto_g`|**INT**|Peso do produto em gramas.|
|`comprimento_produto_cm`|**INT**|Comprimento do produto em centímetros.|
|`altura_produto_cm`|**INT**|Altura do produto em centímetros.|
|`largura_produto_cm`|**INT**|Largura do produto em centímetros.|

<br>

### 5. Tabela pedidos

Armazena informações sobre os pedidos realizados.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_pedido`|**VARCHAR(255)**|Identificador único do pedido (chave primária).|
|`id_cliente`|**VARCHAR(255)**|Identificador do cliente que fez o pedido.|
|`status_pedido`|**VARCHAR(50**)|Status do pedido (ex.: aprovado, enviado).|
|`data_compra`|**DATETIME**|Data de realização do pedido.|
|`data_aprovacao_pagamento`|**DATETIME**|Data de aprovação do pagamento.|
|`data_envio_transportadora`|**DATETIME**|Data de envio para a transportadora.|
|`data_entrega_cliente`|**DATETIME**|Data de entrega ao cliente.|
|`data_entrega_estimada`|**DATETIME**|Data estimada para a entrega.|

**Relacionamentos:**

**Chave estrangeira:** `id_cliente` -> `clientes(id_cliente)`.

<br>

### 6. Tabela itens_pedido

Armazena os itens contidos nos pedidos.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_pedido`|**VARCHAR(255)**|Identificador do pedido (parte da chave primária).|
|`id_item_pedido`|**INT**|Identificador do item no pedido (auto incremento).|
|`id_produto`|**VARCHAR(255)**|Identificador do produto.|
|`id_vendedor`|**VARCHAR(255)**|Identificador do vendedor do item.|
|`preco`|**DECIMAL(10, 2)**|Preço do item no pedido.|
|`valor_frete`|**DECIMAL(10, 2)**|Valor do frete do item.|

**Relacionamentos:**

**Chaves estrangeiras:**

`id_pedido` -> `pedidos(id_pedido)`.
`id_produto` -> `produtos(id_produto)`.
`id_vendedor` -> `vendedores(id_vendedor)`.

<br>

### 7. Tabela pagamentos

Armazena as informações sobre os pagamentos realizados.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_pedido`|**VARCHAR(255)**|Identificador do pedido associado.|
|`sequencial_pagamento`|**INT**|Sequência do pagamento para pedidos com múltiplos.|
|`tipo_pagamento`|**VARCHAR(50)**|Tipo de pagamento utilizado.|
|`parcelas_pagamento`|**INT**|Número de parcelas do pagamento.|
|`valor_pagamento`|**DECIMAL(10, 2)**|Valor pago.|

**Relacionamentos:**

**Chave estrangeira:** `id_pedido` -> `pedidos(id_pedido)`.

<br>

### 8. Tabela avaliacoes

Armazena as avaliações feitas pelos clientes sobre os pedidos.

|**Coluna**|**Tipo**|**Descrição**|
|---|---|---|
|`id_avaliacao`|**VARCHAR(255)**|Identificador único da avaliação (chave primária).|
|`id_pedido`|**VARCHAR(255)**|Identificador do pedido avaliado.|
|`nota_avaliacao`|**INT**|Nota atribuída pelo cliente (1 a 5).|
|`titulo_comentario`|**VARCHAR(255)**|Título do comentário.|
|`mensagem_comentario`|**TEXT**|Detalhamento do comentário.|
|`data_criacao_avaliacao`|**DATETIME**|Data de criação da avaliação.|
|`data_resposta_avaliacao`|**DATETIME**|Data de resposta à avaliação.|

**Relacionamentos:**

**Chave estrangeira:** `id_pedido` -> `pedidos(id_pedido)`.

<br>

## Diagrama deEntidade e Relacionamento (DER)

O modelo apresenta as seguintes relações principais:

- Clientes e Vendedores conectados à tabela `geolocalizacao.
- Pedidos conectados aos clientes, itens_pedido e pagamentos.
- Produtos e vendedores conectados aos itens_pedido.
- Avaliações ligadas aos pedidos.
