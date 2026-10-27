# Sistema de Gestão para Confeitaria

Aplicação web educacional para cadastro de pedidos, acompanhamento de vendas e controle de valores recebidos e pendentes em uma confeitaria.

## Sobre o projeto

O sistema funciona diretamente no navegador e reúne, em uma única página, recursos para registrar vendas, editar pedidos, acompanhar pagamentos, filtrar resultados por período e gerar backups dos dados.

O nome da confeitaria pode ser personalizado pelo usuário. Os pedidos e a configuração do nome são armazenados localmente no navegador por meio do `localStorage`.

## Funcionalidades

- Personalização do nome da confeitaria.
- Cadastro de pedidos com data, cliente, produto, valor e situação do pagamento.
- Edição e exclusão de pedidos cadastrados.
- Identificação visual de pedidos pagos e pendentes.
- Relatório com total recebido e total a receber.
- Filtros por mês e ano.
- Listagem detalhada das vendas do período selecionado.
- Geração de mensagem formatada para compartilhamento pelo WhatsApp.
- Exportação dos pedidos para arquivo JSON.
- Importação e restauração de backup em JSON.
- Exclusão conjunta das vendas exibidas no filtro selecionado.
- Interface responsiva voltada para uso em computadores e dispositivos móveis.

## Tecnologias utilizadas

- HTML5
- CSS3
- JavaScript Vanilla
- Web Storage API (`localStorage`)
- FileReader API
- Blob API

## Estrutura do projeto

```text
sistema-confeitaria/
├── index.html
└── README.md
```

A estrutura, os estilos e a lógica da aplicação estão concentrados no arquivo `index.html`.

## Como executar

1. Baixe os arquivos do projeto.
2. Mantenha o `index.html` e o `README.md` na mesma pasta.
3. Abra o arquivo `index.html` em um navegador moderno.
4. No primeiro acesso, informe o nome da confeitaria ou deixe o campo vazio.
5. Cadastre os pedidos e utilize os filtros para consultar as vendas.

Não é necessário instalar dependências, executar comandos ou configurar banco de dados.

## Cadastro de pedidos

Cada pedido utiliza os seguintes dados:

| Campo | Descrição |
|---|---|
| Data | Data associada à venda |
| Cliente | Nome do cliente |
| Produto | Produto encomendado |
| Valor | Valor da venda em reais |
| Status | Indica se o pedido foi pago ou está pendente |

Todos os campos precisam ser preenchidos para que a venda seja gravada.

## Relatório de vendas

O relatório apresenta os valores de acordo com o mês e o ano selecionados:

- **Recebido:** soma dos pedidos marcados como pagos.
- **A receber:** soma dos pedidos marcados como pendentes.

Também é possível selecionar todos os meses ou todos os anos disponíveis nos filtros.

## Edição e exclusão

Na lista de vendas, cada pedido possui ações para:

- editar os dados cadastrados;
- gerar uma mensagem com os detalhes do pedido;
- apagar individualmente o registro.

A opção **Limpar Vendas do Período Selecionado** remove todos os registros correspondentes aos filtros ativos após uma confirmação do usuário.

## Compartilhamento do pedido

A ação **Pedido** monta uma mensagem com as informações da venda e abre a interface de compartilhamento do WhatsApp.

Antes de publicar ou distribuir o projeto, revise os dados fixos presentes no modelo da mensagem, especialmente informações de pagamento. Evite manter dados pessoais ou financeiros reais diretamente no código-fonte.

## Armazenamento local

Os pedidos são gravados no `localStorage` usando a chave:

```text
pedidos_mel_v6
```

O nome personalizado da confeitaria é armazenado na chave:

```text
nome_confeitaria
```

Os dados permanecem vinculados ao navegador e ao dispositivo utilizados. A limpeza dos dados do navegador pode apagar as informações armazenadas.

## Backup e restauração

### Exportar backup

O botão **Backup (Salvar)** gera um arquivo JSON contendo os pedidos cadastrados.

### Restaurar backup

O botão **Abrir Backup** permite selecionar um arquivo JSON exportado anteriormente. Após a leitura, os pedidos do arquivo passam a substituir os dados atuais da aplicação.

Recomenda-se manter cópias periódicas dos backups em um local seguro.

## Personalização

O visual pode ser adaptado diretamente no CSS do `index.html`. O projeto utiliza principalmente tons de rosa, branco, verde e vermelho para diferenciar ações, pagamentos e pendências.

O nome da confeitaria pode ser alterado pelo botão disponível no cabeçalho, sem necessidade de editar o código.

## Compatibilidade

A aplicação requer um navegador moderno com JavaScript e `localStorage` habilitados.

A geração da mensagem utiliza uma página externa do WhatsApp e, portanto, depende de acesso à internet para abrir o serviço.

## Limitações

- Os dados não são sincronizados automaticamente entre dispositivos.
- Não há autenticação de usuários.
- Não existe banco de dados remoto.
- A restauração depende de um arquivo JSON válido e compatível.
- O controle financeiro é simplificado e não substitui sistemas contábeis ou fiscais.

## Autor

**Alberto de Campos Neto**

## Aviso

> Este projeto é uma demonstração educacional desenvolvida para estudos de HTML, CSS e JavaScript. A empresa mencionada é fictícia e qualquer semelhança com empresas reais é mera coincidência.
