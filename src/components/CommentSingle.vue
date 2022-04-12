<template>
  <li>
    <img class="post-img" :src="text.authorImg" />
    <small>{{ text.author }} </small>
    <p class="post-comment">"{{ text.text }} "</p>
  </li>
</template>

<script>
export default {
  props: ["text"],
};
</script>

<style lang="scss" scoped>
li {
  list-style: none outside none;
  text-align: left;
  padding: 10px 0;
  border-bottom: 1px solid #555;
}

ul {
  margin: 0;
  padding: 0 35px;
}

hr {
  margin: 25px 0 0 32px;
  width: 300px;
  border-top: 0;
  border-bottom: 1px solid #555;
}

input {
  font-family: "Playfair Display", serif;
  width: 280px;
  margin: 30px 0;
  padding: 8px 10px;
  outline: 0;
}

.post-img {
  border: 3px solid white;
  float: left;
  margin: 0 15px 0 -2px;
  transition: 0.3s all ease;
}

.post-comment {
  margin: 0 0 5px 0;
}
</style>