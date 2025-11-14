# Ficha Prática 1: Processamento de Formulário com PHP

Este repositório contém um projeto simples que demonstra a submissão de dados de um formulário HTML para um script PHP, onde os dados são processados e é apresentado um resultado com base em lógica condicional.

## Funcionalidades

O projeto realiza as seguintes operações:

1.  **Recolha de Dados:** Um formulário HTML (`form.html`) recolhe o nome, idade e uma palavra-passe do utilizador.
2.  **Processamento de Dados:** O script PHP (`resultado.php`) recebe os dados submetidos via método POST.
3.  **Saudação Personalizada:** Apresenta uma saudação ao utilizador com o nome fornecido.
4.  **Classificação Etária:** Classifica o utilizador em uma das seguintes categorias com base na idade:
    *   Criança (Idade `< 12`)
    *   Adolescente (Idade `12` a `17`)
    *   Adulto (Idade `> 17`)
5.  **Análise de Força da Palavra-Passe:** Avalia a força da palavra-passe com base no seu comprimento:
    *   Fraca (Comprimento `< 5`)
    *   Média (Comprimento `5` a `8`)
    *   Forte (Comprimento `> 8`)

## Estrutura do Projeto

O projeto está organizado na seguinte estrutura de diretórios:

```
.
└── fp01/
    ├── form.html
    └── resultado.php
```

| Ficheiro | Descrição |
| :--- | :--- |
| `fp01/form.html` | Contém o formulário HTML para a entrada de dados. |
| `fp01/resultado.php` | Script PHP que processa os dados do formulário, classifica a idade e avalia a força da palavra-passe. |

## Requisitos

Para executar este projeto, é necessário um ambiente de servidor web que suporte PHP. As opções mais comuns incluem:

*   **XAMPP**
*   **WAMP**
*   **MAMP**
*   Um servidor web (como Apache ou Nginx) com o módulo PHP instalado.

## Como Executar

1.  **Configuração do Servidor:** Certifique-se de que tem um servidor web com PHP configurado (por exemplo, XAMPP).
2.  **Localização dos Ficheiros:** Coloque a pasta `fp01` no diretório raiz do seu servidor web (por exemplo, `htdocs` no XAMPP).
3.  **Acesso:** Abra o seu navegador e navegue para o ficheiro `form.html`:
    ```
    http://localhost/fp01/form.html
    ```
4.  **Interação:** Preencha o formulário e clique em "Enviar" para ver o resultado processado pelo `resultado.php`.

## Detalhes Técnicos

### `form.html`

O formulário utiliza o método `POST` para enviar os dados, garantindo que a informação (incluindo a palavra-passe) não é exposta diretamente no URL.

```html
<form action="resultado.php" method="POST">
    <!-- Campos: nome, idade, senha -->
</form>
```

### `resultado.php`

O script PHP utiliza a superglobal `$_POST` para aceder aos dados. A lógica de classificação é implementada com estruturas `if-elseif-else`.

**Lógica de Classificação Etária:**

| Condição | Classificação |
| :--- | :--- |
| `$idade < 12` | Criança |
| `$idade >= 12 && $idade <= 17` | Adolescente |
| `$idade > 17` | Adulto |

**Lógica de Força da Palavra-Passe:**

| Comprimento (`strlen($senha)`) | Força | Cor de Destaque |
| :--- | :--- | :--- |
| `< 5` | Fraca | Vermelho |
| `5` a `8` | Média | Laranja |
| `> 8` | Forte | Verde |
