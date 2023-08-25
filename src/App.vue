<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";
export default {
  components: {
    PostForm, PostList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Пост о JavaScrip 1', body: 'JavaScript - универсальный язык программирования 1'},
        {id: 2, title: 'Пост о JavaScrip 2', body: 'JavaScript - универсальный язык программирования 2'},
        {id: 3, title: 'Пост о JavaScrip 3', body: 'JavaScript - универсальный язык программирования 3'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  }
}
</script>
<!-- Полная запись:  v-on:click  v-bind:posts -->
<!-- Короткая запись:    @click        :posts -->
<template>
  <div class="app">
    <post-form
        @create="createPost"
    />
    <post-list
        :posts="posts"
    />
  </div>
</template>

<!-- scoped говорит о применимости стилей только к этому компоненту и недопустимости извне-->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>