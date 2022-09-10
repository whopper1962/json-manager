<template>
  <div>
    <h1>This is {{ contentId }}</h1>
    <textarea></textarea>
  </div>
</template>
<script>
export default {
  data () {
    return {
      contentId: null
    };
  },
  created () {
    this.contentId = this.$route.params['content_id'];
  },
  methods: {
    getDetails () {
      axios.get(`/${this.contentId}`).then((response) => {
        console.log(response);
      }).catch((error) => {});
    }
  }
}
</script>