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
podemos ter outra tag caso ele tenha setup como propriedade <script setup>. Já 
o style aceita múltiplas tags. 

- Na tag script o 'export default' deve ser um vue component options object, deve 
retornar um objeto.

- Na tag style podemos ter 'scoped' e 'module' como atributo que ajudam a 
encapsular os estilos do componente atual.

* mais sobre script setup: https://vuejs.org/api/sfc-script-setup.html
* mais sobre single-file componente em: https://vuejs.org/api/sfc-spec.html
* mais sobre css scoped e module: https://vuejs.org/api/sfc-css-features.html#scoped-css

### Declarações Condicionais (Diretivas)

- Diretivas são instruções que orietam o código a uma ação específica, regras 
que permite a realização de uma tarefa. No vue as diretivas serão 'tag' especiais 
que serão incluídas nos elementos HTML como se fossem attributos e que irão aplicar 
algum comportamento especial a esse atributo.

- Apesar das diretivas serem aplicados semelhante a um atributo normal, elas não 
são atributos, pois elas executam ações determinados por uma função ou instrução.
As diretivas são escritos com o prefixo 'v-' seguido do nome dela. Podemos também 
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

- renderiza um elemento múltiplas vezes baseado no data, assim como o for normal, 
podemos iterar sobre objetos, arrays, números, string ou qualquer outro iterável.

- contém uma sintaxe especial: v-for="(item, index) in array". Podemos passar como 
argumento o item atual que está sendo iterado e também receber o seu index, o que 
é opcional. Por padrão o v-for não move o elemento de local, para formarços ele 
a organizar os elementos, o vue precisa de uma diretiva 'v-bind:key' para que ele 
possa identificar cada item iterado.