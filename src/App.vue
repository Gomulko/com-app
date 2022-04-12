<template>
  <div>
    <img
      src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/vue-post-photo.jpg"
      class="main-photo"
    />
    <img
      src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/28963/vue-main-profile.jpg"
      class="main-profile"
    />
    <div class="main-info">
      <span class="name">Julianne Delfina</span>
      <h3>"It's lovely after it rains"</h3>
    </div>
    <hr />
    <ul>
      <comment-single
        v-for="comment in comments"
        :key="comment"
        :text="comment"
      />
    </ul>
    <input
      v-model="newComment"
      @keyup.enter="addComment"
      placeholder="Add a comment"
    />
  </div>
</template>

<script>
import CommentSingle from "./components/CommentSingle.vue";
export default {
  components: {
    CommentSingle,
  },
  data() {
    return {
      newComment: "",
    };
  },
  computed: {
    comments() {
      return this.$store.state.comments;
    },
  },
  methods: {
    addComment() {
      this.$store.commit("addComment", this.newComment);
    },
  },
};
</script>

<style lang="scss" >
body {
  font-family: "Playfair Display", serif;
  background: #888;
}

#app {
  background: #212222;
  color: #fff;
  letter-spacing: 0.04em;
  text-align: center;
  margin: 60px;
  width: 370px;
  margin: 0 auto;
  display: table;
  padding: 20px;
  line-height: 1.4em;
}

.name {
  color: #ccc;
}

small {
  color: #bbb;
  font-size: 10px;
}

h3 {
  margin: 5px 0 4px;
}

.main-photo {
  width: 300px;
}

.main-profile {
  float: left;
  border: 3px solid white;
  margin: -25px 0 0 20px;
  position: relative;
  width: 80px;
}

.main-info {
  float: left;
  padding: 10px 20px;
  text-align: left;
  margin-bottom: 15px;
  &:after {
    content: "";
    display: table;
    clear: both;
  }
}
</style>