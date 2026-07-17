COMPILADOR LMS
==============

Compilador com interface grafica (Swing) para a linguagem LMS, uma
linguagem de programacao de sintaxe estilo Pascal. O projeto implementa
analise lexica e sintatica, exibindo os tokens reconhecidos e o
resultado da analise em uma tabela na propria interface.


SOBRE A LINGUAGEM LMS
----------------------

- Letras: A-Z, a-z
- Digitos: 0-9
- Operadores aritmeticos: + - * /
- Operadores relacionais: = < > <> >= <=
- Simbolos especiais: , ; . ( ) : .. [ ] ' _
- Comentarios delimitados por (* e *)

Exemplos de programas validos na linguagem estao em
EXEMPLOS_VALIDACAO.isi.


STACK
-----

- Java (JDK 21, testado com Eclipse Temurin - deve funcionar em
  qualquer JDK 8+)
- Swing (interface grafica)
- Projeto originalmente criado no IntelliJ IDEA (arquivo .iml)


ESTRUTURA
---------

src/
|-- compilador/       Analisador lexico/sintatico (Analisador, Token, Simbolo)
|-- doMain/           Classe main (MainClass)
|-- exceptions/       Excecoes customizadas
|-- img/              Icones usados na interface
|-- pathController/   Manipulacao de arquivos (abrir/salvar programas .isi)
|-- util/             Modelos de tabela (tokens e analise sintatica)
`-- view/             Interface grafica (Home)


COMO COMPILAR E RODAR
----------------------

Pre-requisito: JDK 8 ou superior instalado.

Compilar:
   find src -iname "*.java" > sources.txt
   javac -d out/production -encoding UTF-8 @sources.txt

Copiar os icones para o classpath (necessario porque javac nao copia
recursos automaticamente):
   cp -r src/img out/production/

Rodar:
   java -cp out/production doMain.MainClass

A interface grafica abre com opcoes para carregar um arquivo .isi,
executar a analise lexica/sintatica e visualizar os tokens
reconhecidos.


OBSERVACOES
-----------

- Este e um projeto academico de compiladores, focado no processo de
  analise lexica/sintatica - nao gera codigo executavel (nao ha etapa
  de geracao de codigo).

- Se abrir no IntelliJ IDEA, a IDE cuida automaticamente da copia de
  recursos (img/) para o diretorio de saida; ao compilar manualmente
  via javac, esse passo precisa ser feito a mao (comando acima).
