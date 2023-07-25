<template>
  <div class="post-card">
    <h3>Título lorem</h3>
    <p>Lorem ipsum dolor sit amet.</p>
    <PostButton />
  </div>
</template>

<script lang="ts" setup>
import PostButton from "./PostButton.vue";

</script>

<style scoped>
.post-card {
  width: 100%;
  border-radius: 1rem;
  padding: 1rem;
  margin: .5rem;
  border: 1px solid #ccc;
}
</style>
