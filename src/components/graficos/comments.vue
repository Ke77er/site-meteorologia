<template>
    <div class="container">
    <h1>Comentários</h1>
    <hr />
    <FormTodo v-on:add-todo="addComment"></FormTodo>
    <div class="list-group">
    <p v-if="comments.length <= 0">Sem comentários pse...</p>
    <div v-else class="list-group-item" v-for="(comment, index) in allComments" v-bind:key="index">
        <span class="comment__author">Autor: <strong>{{ comment.name }}</strong></span>
        <p>{{ comment.message }}</p>
        <div>
        <a href="#" title="Excluir" v-on:click.prevent="removeComment(index)">Excluir</a>
        </div>
    </div>
    </div>
    <hr />
  </div>
</template>
<script>
import FormTodo from './formtodo.vue';
export default {
    name:'Comments',
  components: {
    FormTodo
  },
  data() {
    return {
      comments: []
    }
  },
  methods: {
    addComment(comment) {
      this.comments.push(comment);
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  },
  computed: {
    allComments() {
  return this.comments.map(comment => Object.assign({}, comment, {
    name: comment.name.trim() === '' ? 'Anônimo' : comment.name
  }));
}
  },
  watch: {
    comments(val) {
      console.log('val', val)
    }
  }
}
</script>
<style>
.list-group {
  max-height: 310px;
  overflow-y: auto;
}
</style>