# Compilador LMS

Compilador com interface gráfica (**Swing**) para a linguagem **LMS**, uma linguagem de programação de sintaxe estilo Pascal. O projeto implementa **análise léxica e sintática**, exibindo os tokens reconhecidos e o resultado da análise em uma tabela na própria interface.

## Sobre a linguagem LMS

- **Letras:** A-Z, a-z
- **Dígitos:** 0-9
- **Operadores aritméticos:** `+` `-` `*` `/`
- **Operadores relacionais:** `=` `<` `>` `<>` `>=` `<=`
- **Símbolos especiais:** `,` `;` `.` `(` `)` `:` `..` `[` `]` `'` `_`
- **Comentários:** delimitados por `(*` e `*)`

Exemplos de programas válidos na linguagem estão em `EXEMPLOS_VALIDACAO.isi`.

## Stack

- Java (JDK 21, testado com Eclipse Temurin — deve funcionar em qualquer JDK 8+)
- Swing (interface gráfica)
- Projeto originalmente criado no IntelliJ IDEA (arquivo `.iml`)

## Estrutura

```
src/
├── compilador/       Analisador léxico/sintático (Analisador, Token, Simbolo)
├── doMain/           Classe main (MainClass)
├── exceptions/       Exceções customizadas
├── img/              Ícones usados na interface
├── pathController/   Manipulação de arquivos (abrir/salvar programas .isi)
├── util/             Modelos de tabela (tokens e análise sintática)
└── view/             Interface gráfica (Home)
```

## Como compilar e rodar

**Pré-requisito:** JDK 8 ou superior instalado.

Compilar:

```bash
find src -iname "*.java" > sources.txt
javac -d out/production -encoding UTF-8 @sources.txt
```

Copiar os ícones para o classpath (necessário porque `javac` não copia recursos automaticamente):

```bash
cp -r src/img out/production/
```

Rodar:

```bash
java -cp out/production doMain.MainClass
```

A interface gráfica abre com opções para carregar um arquivo `.isi`, executar a análise léxica/sintática e visualizar os tokens reconhecidos.

## Observações

- Este é um projeto acadêmico de compiladores, focado no processo de análise léxica/sintática — **não gera código executável** (não há etapa de geração de código).
- Se abrir no IntelliJ IDEA, a IDE cuida automaticamente da cópia de recursos (`img/`) para o diretório de saída; ao compilar manualmente via `javac`, esse passo precisa ser feito à mão (comando acima).

## Licença

[MIT](LICENSE).
