<!-- 
Fare l'esercizio della to do list per ogni todo avremo un oggetto, formato da due proprietà:
text, una stringa che indica il testo del todo
done, un booleano (true/false) che indica se il todo è stato fatto oppure no
MILESTONE 1
Stampare all'interno di una lista HTML un item per ogni todo. Se la proprietà done è uguale a true, visualizzare il testo del todo sbarrato.
MILESTONE 2
Visualizzare a fianco ad ogni item ha una "x": cliccando su di essa, il todo viene rimosso dalla lista.
-->
<script>
export default {
  data() {
    return {
      listTodo: [
        { todo: 'andare in palestra', done: true },
        { todo: 'andare a fare la spesa', done: false },
        { todo: 'consegnare la milestone 2', done: true },
        { todo: 'studiare', done: true },
        { todo: 'andare a calcetto', done: false },
        { todo: 'mettersi a dieta', done: true },
      ],
      isVisibile: true,
    }
  },
  methods: {
    deleteItems(index) {
      this.listTodo.splice(index, 1);
    }

  }
}
</script>

<template>
  <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
      integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
      crossorigin="anonymous" referrerpolicy="no-referrer" />
  </head>
  <main>
    <div class="container">
      <h1>Todo list</h1>
      <ul>
        <div v-for=" (item, index)  in  listTodo ">
          <li v-if="item.done !== true">{{ item.todo }} <i @click="deleteItems(index)"
              class="fa-regular fa-circle-xmark"></i>
          </li>
          <li v-else class="fact">{{ item.todo }} <i @click="deleteItems(index)" class="fa-regular fa-circle-xmark"></i>
          </li>

        </div>
      </ul>
    </div>
  </main>
</template>


<style scoped></style>
