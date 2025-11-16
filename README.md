**Introdução ao React**

Como Começar com React (pesquisem sobre React, Usestate e hooks).

**O que é JSX?**
JSX é uma linguagem parecida com HTML, mas usada dentro do JavaScript. Ela permite escrever elementos visuais (como div, h1, etc.) diretamente no código React.

**O que é um Componente?**
Um componente é uma função que retorna JSX. Ele representa uma parte da interface, como um botão, uma lista ou um formulário.

**Diferença entre JSX e HTML**
JSX usa className em vez de class.
JSX precisa de uma única tag pai (como <div> envolvendo tudo).
JSX permite usar variáveis e funções dentro das tags com {}.

**Explicando o useState**
useState é um hook (função especial do React) que guarda valores que mudam.
Ele devolve um array com dois elementos:
o valor atual (tarefas)
e a função que atualiza esse valor (setTarefas).

**Manipulando Arrays e Propriedades**
Manipulação de Arrays (Lista de Tarefas)
A manipulação de arrays no estado do React deve ser feita de forma imutável. Isso significa que, em vez de modificar o array existente (tarefas), você deve criar um novo array com a alteração desejada e, em seguida, passar esse novo array para a função setTarefas.

**1° Adicionar Item (Imutável):**

No código:

JavaScript
setTarefas([...tarefas, input]);
...tarefas (Spread Operator): Cria uma cópia de todos os elementos do array tarefas existente.
input: Adiciona o valor atual do input ao final desse novo array.
O setTareiras recebe o novo array completo.

**2° Listar Itens:**

No código:

JavaScript
<ul>
  {tarefas.map((tarefa, index) => (
    <li key={index}>{tarefa}</li>
  ))}
</ul>
tarefas.map(...): É o método padrão do JavaScript para iterar sobre um array e retornar um novo array. Neste caso, ele retorna um novo array de elementos JSX (<li>).
{ ... }: As chaves são usadas para incorporar a lógica JavaScript (map) dentro do JSX.
key={index}: O React exige que cada item em uma lista dinâmica tenha uma propriedade key única para ajudá-lo a identificar quais itens mudaram, foram adicionados ou removidos.

**Propriedades (Props) dos Componentes**
No seu código, você usa props implicitamente em elementos HTML:
value={input}: O valor do campo de entrada é controlado pelo estado input.
onChange={e => setInput(e.target.value)}: Define uma função de callback (propriedade) que é chamada toda vez que o valor do input muda. Ela usa e.target.value (o novo texto) para atualizar o estado input via setInput.
Se você estivesse usando componentes próprios (ex: <Botao nome="Adicionar" />), nome seria uma propriedade que você passaria para o componente Botao.
