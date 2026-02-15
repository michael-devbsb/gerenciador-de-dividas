# Registro de Dívidas

Gerenciador de dívidas em formato de mural, com interface visual inspirada em post-its e estética brutalista.

## Descrição

O **Registro de Dívidas** é uma aplicação web em uma única página (`index.html`) que permite cadastrar, visualizar, editar e acompanhar dívidas de forma organizada. Os registros são exibidos como post-its em um mural, com resumos de totais, filtros e ordenação.

## Características

### Funcionalidades principais

- **Cadastro de dívidas**: Nome, valor obtido, quantidade de parcelas, valor mensal, valor total e observações
- **Visualização em mural**: Cada dívida aparece como um “post-it” com cores diferentes para pendentes (vermelho) e pagas (azul)
- **Edição**: Alterar qualquer informação de uma dívida já cadastrada
- **Exclusão**: Remover dívidas com confirmação
- **Marcar como pago**: Alterar o status de pendente para pago
- **Filtros**: Exibir todas, apenas pendentes ou apenas pagas
- **Ordenação**: Por data, valor, nome ou status
- **Backup**: Exportar e importar dados em JSON

### Resumos financeiros

- **Total de dívidas**: Soma de todos os valores
- **Pendentes**: Valor total das dívidas ainda não pagas
- **Pagas**: Valor total das dívidas já pagas

## Tecnologias

- **HTML5** – Estrutura da página
- **CSS3** – Estilização com variáveis CSS, layout responsivo e animações
- **JavaScript (Vanilla)** – Lógica da aplicação sem frameworks
- **LocalStorage** – Armazenamento local dos dados

## Design

### Estética

- **Tema**: Visual de papel e post-its
- **Fontes**: Libre Baskerville (títulos) e IBM Plex Mono (dados)
- **Cores**:
  - Papel: `#f4f1ea`
  - Grafite: `#2d2a26`
  - Sangue (pendentes): `#8b2635`
  - Caneta azul (pagas): `#1e3a5f`
- **Recursos visuais**: Textura de papel, efeito de film grain, post-its com leve rotação e clip-path

### Responsividade

Em telas menores que 900px, o layout passa a ser em coluna, com elementos empilhados verticalmente.

## Como usar

### Executar a aplicação

1. Clone ou baixe o repositório
2. Abra o arquivo `index.html` em um navegador web
3. Não é necessário servidor; o arquivo funciona localmente

### Cadastrar uma dívida

1. Clique em **+ Nova Dívida**
2. Preencha os campos obrigatórios:
   - Nome da dívida
   - Valor obtido (R$)
   - Quantidade de parcelas
   - Valor mensal (R$)
   - Valor total (R$), calculado automaticamente ou informado manualmente
3. Opcional: adicione observações
4. Clique em **+ Adicionar Dívida**

### Backup dos dados

- **Exportar**: Clique em **Exportar** para baixar um arquivo JSON com todas as dívidas
- **Importar**: Clique em **Importar** e selecione um arquivo JSON previamente exportado (substitui os dados atuais)

## Estrutura dos dados

Cada dívida é armazenada com:

| Campo              | Tipo     | Descrição                          |
|--------------------|----------|------------------------------------|
| `id`               | number   | Identificador único (timestamp)    |
| `nome`             | string   | Nome da dívida                     |
| `valorObtido`      | number   | Valor inicial obtido               |
| `quantidadeParcelas` | number | Número de parcelas                 |
| `valorMensal`      | number   | Valor de cada parcela              |
| `valorTotal`       | number   | Valor total da dívida              |
| `observacao`       | string   | Observações                        |
| `status`           | string   | `"pendente"` ou `"pago"`           |
| `dataCriacao`      | string   | Data de criação (ISO)              |
| `dataAtualizacao`  | string   | Data da última edição (ISO)        |
| `dataPagamento`    | string   | Data do pagamento (ISO), se pago   |

## Licença

Projeto para uso pessoal/educacional. Use conforme sua necessidade.
