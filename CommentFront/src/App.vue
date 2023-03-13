<template>
  <div id="app">
    <h1>Formulaire de commentaire</h1>
    <comment-form></comment-form>
  </div>
</template>

<script>
import CommentForm from './components/CommentForm.vue';

export default {
  name: 'App',
  components: {
    CommentForm,
  },
};
</script>
