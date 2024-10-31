
## Sobre

[[XPath]] - (*XML Path Language*) é um método de seleção de nós [[XML]], muito utilizado em ambientes de automatização de tarefas, pela sua versatilidade e precisão. 

## Site para testar: www.xpather.com


## Nós

#### Classificando Nós

Os nós analisados podem ser classificados em 7 tipos diferentes:

1. **Element**: Representa um elemento HTML ou XML, como uma tag. Por exemplo, `<div>`, `<p>`, ou `<a>`.
   
2. **Attribute**: Representa os atributos de um elemento, que são pares nome/valor dentro da tag de abertura de um elemento. Por exemplo, `href="https://example.com"` no elemento `<a>`.
   
3. **Text**: Contém o texto dentro de um elemento. Por exemplo, o conteúdo textual entre as tags `<p>Texto aqui</p>`.
   
4. **Namespace**: Representa os namespaces declarados em um elemento. Namespaces ajudam a evitar conflitos de nomes em documentos XML que combinam dados de diferentes fontes.
   
5. **Processing-instruction**: Fornece instruções para a aplicação que processa o documento XML. Por exemplo, `<?xml-stylesheet type="text/xsl" href="style.xsl"?>`.
   
6. **Comment**: Representa os comentários no código XML ou HTML, como `<!-- Este é um comentário -->`.
   
7. **Root**: O nó que representa o documento completo. Todos os outros nós estão subordinados a este nó.


#### Selecionando Nós

Podemos selecionar nós de 6 fomas diferentes:

- **button** -> Seleciona todos os elementos chamados "button"

- **/button** -> Localiza o Root chamado button (só funciona se o button realmente for o root) 

- **/button/input** -> Seleciona todos os filhos  de "button" chamados "input" de primeira intância

- **//button**  -> Seleciona todos os "button", mesmo se ele não tiver na pasta raiz

- **/button//input**  -> Seleciona todos os "input" que estão dentro de "button", mesmo se não for na primeira instância

- **//@id** -> Seleciona todos os nós que tiverem o atributo "id"

#### Especificando Nós

Para deixar nossa seleção de nós ainda mais precisa, podemos especificar nossa busca

- **/button/input[1]** -> Seleciona o primeiro item encontrado

- **/button/input[last()]** -> Seleciona o último item encontrado

- **/button/input[last()-1]** -> Seleciona o penúltimo item encontrado

- **/button/input[position()<3]** -> Seleciona os items 1 e 2

- **/div[@id]** -> Seleciona a div que tem o atributo ID

- **/div[@name='Teste']** -> Seleciona a div que tem o Name igual há "Teste"

- **/div[@name='principal']/h1** -> Seleciona o H1 da DIV com o Name igual a "principal"

- **/div[@name='principal']/h1[text()='Seja Bem-vindo']** -> Seleciona o H1 da DIV com o Name igual a "principal"

#### Nós Genéricos e Alternativos

- ***\** -> Qualquer tipo de Elemento

- **@*\** -> Qualquer tipo de Atributo

- **node()** -> Seleciona todos os nós

- **//div | /button/input** -> Seleciona todas as Div e todos os inputs dentro dos botões (**OR**)


#### Localização de Nós

- **child::div** -> Seleciona todas as divs que são filhas do nó atual

- **attribute::id** -> Seleciona só o atributo ID

- **descendant::div** -> Seleciona todos os descendentes (filhos, netos, etc...) que são divs

- **ancestor::div** -> Seleciona todas divs que antecedem esse nó (pais, avós, etc...)

- **ancestor-or-self::div** -> Seleciona todas as divs que antecedem esse nó e ele mesmo (se for uma div)

- **child::\*/child::button** -> Busca por um bisneto que seja um button

#### Operações

- **|** -> Seleciona dois tipos de Nós

- **+** -> Adição

- **-** -> Subtração

- **\*** -> Multiplicação

- **div** -> Divisão

- **mod** -> Resto da divisão

- **=** -> Igual a ...

- **!=** -> Diferente de ...

- **<** -> Menor que ...

- **<=** -> Menor igual a ...

- **>** -> Maior que ...

- **>=** -> Maior igual a ...

- **OR** -> Seleciona um valor que é igual a um atributo ou outro. Ex: *preco=10 or preco<5* 

- **AND** -> Seleciona um valor que os dois atributos correspondem a query. Ex: *preco<10 and preco > 100*