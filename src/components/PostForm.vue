<script>

export default {
  data() {
    return {
      post: {
        title: '',
        body: ''
      },
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      // передача значений от дочернего элемента родительскому
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: ''
      };
    }
  }
}

</script>

<template>
  <form class="form" @submit.prevent>
    <h4>Создание поста</h4>
    <!--  v-bind:value="post.title"
          @input="post.title = $event.target.value"
    -->
    <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Название"
    >
    <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Описание"
    >
    <button
        @click="createPost"
        class="btn"
    >Опубликовать</button>
  </form>
</template>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  align-self: flex-end;
  margin-top: 15px;
  padding: 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>