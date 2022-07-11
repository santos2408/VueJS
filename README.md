# The Progressive JavaScript Framework

### Single-File Components

- É um componente de arquivo único com extensão (.vue) que nos permite encapsular 
o html, estilo e a lógica de um componente num só lugar. Com esse formato, isso 
nos permite importar o componente com toda sua lógica e estilo e aplica-lo em 
qualquer parte do código. Procure colocar o nome do arquivo igual ao nome do 
componente.

- Consiste de três blocos: template, script e style, mas aceitam opcionalmente
blocos customizados adicionais.

- O componente só pode ter um bloco <template> e <script> por vez, mas para o script 
podemos ter outra tag caso ele tenha 'setup' como propriedade <script setup>. Já 
o style aceita múltiplas tags. 

- Na tag script o 'export default' deve ser um vue component options object, deve 
retornar um objeto. 'export default { logica }'

- Na tag style podemos ter 'scoped' e 'module' como atributo que ajudam a 
encapsular os estilos do componente atual.

* mais sobre script setup: https://vuejs.org/api/sfc-script-setup.html
* mais sobre single-file component em: https://vuejs.org/api/sfc-spec.html
* mais sobre css scoped e module: https://vuejs.org/api/sfc-css-features.html#scoped-css

### Declarações Condicionais (Diretivas)

- Diretivas são instruções que orientam o código a uma ação específica, são regras 
que permitem a realização de uma tarefa. No vue as diretivas serão 'tags' especiais 
que serão incluídas nos elementos HTML como se fossem attributos e que irão aplicar 
algum comportamento especial a esse atributo.

- Apesar das diretivas serem aplicadas semelhantes a um atributo normal, elas não 
são atributos, pois elas executam ações determinados por uma função ou instrução.
As diretivas são escritas com o prefixo 'v-' seguido do nome dela. Podemos também 
criar diretivas customizadas.

#### v-show

- essa diretiva alterna a visilidade do elemento baseado no valor booleano da 
expressão passada como 'argumento' dela. Ela funciona inserindo uma propriedade
'display: none' no elemento em questão, portanto o elemento continua existindo 
na árvore do DOM, mas está apenas invisível.

#### v-if / v-if-else / v-else

- semelhante a v-show, alterna a visilidade do elemento, no entanto ela não 
adiciona a propriedade 'display: none' quando a expressão resulta false, e sim 
remove totalmente o elemento da árvore do DOM. Ou seja, o elemento é destruído 
ou reconstruído dependendo do seu retorno booleano. Use-as em ordem de declaração.

- v-if tem maior prioridade do que v-for, não é recomendado utilizar estas duas 
diretivas num mesmo elemento. Vale lembrar que essa diretiva consome também 
mais poder de processamento do vue, já que ela destrói o elemento e cria novamente.
Das três diretivas, a v-else não espera uma expressão como 'argumento'.

#### v-for

- renderiza um elemento múltiplas vezes baseado no data, assim como o 'for' normal, 
podemos iterar sobre objetos, arrays, números, string ou qualquer outro iterável.

- contém uma sintaxe especial: v-for="(item, index) in array". Podemos passar como 
argumento o item atual que está sendo iterado e também receber o seu index, o que 
é opcional. Por padrão o v-for não move o elemento de local, para forçarmos ele 
a organizar os elementos, o vue precisa de uma diretiva 'v-bind:key' para que ele 
possa identificar cada item iterado.

#### v-bind

- une dinamicamente um ou mais atributos html, ou uma prop de um componente a 
uma expressão. Podemos abreviar usando shorhand apenas inserindo ':' antes do 
atributo. Resumidamente o v-bind torna o atributo dinâmico, podendo receber 
valores através de uma API ou banco de dados.

- podemos utilizar em qualquer atributo, inclusive class e styles, recomenda-se 
também utilzar a forma de shorhand como boas práticas.

- podemos passar valores normais, bem como arrays e objetos com algum valor 
booleano que nos retornará o nome da classe. Em objetos as 'keys' serão os nomes 
das classes e o 'valor' será a expressão que retorna um booleano. Nos arrays 
cada item é o nome da classe, podendo receber também objetos.

#### v-model

- cria uma associação bi-direcional em uma formulário ou componente, é limitado 
a input, select, textarea e componentes.

- basicamente conseguimos passar um valor padrão para um campo, mas se o usuário 
modificar esse campo, com o v-model nós poderemos atualizar dinamicante o valor 
deste campo sem precisar mexer no código. Ele define o valor do formulário com 
base no que o usuário coloca.

- com isso podemos capturar o valor que está sendo digitado pelo usuario e armazenar 
num array, objeto, variável ou banco de dados. Em alguns blocos como radio e checkbox 
é necessário inserir o 'value' do formulário.


// curso intro vue: https://escola.laravue.com.br/course/vuejs-3-intro/episodes/dbc5073a-76d6-48cd-8471-4cdbc65e0774

// parei em eventos: https://vuejs.org/api/built-in-directives.html#v-bind
// parei na criação de uma aplicação: https://vuejs.org/guide/essentials/application.html
// parei em data: https://www.origamid.com/curso/vue-js-completo/