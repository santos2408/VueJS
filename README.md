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