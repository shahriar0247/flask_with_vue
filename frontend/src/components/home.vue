<template>
  <div>
    {{ msg }}
  </div>
</template>

<script>
export default {
  name: "home_",
  data() {
    return {
      msg: "hello from vue",
    };
  },
  methods: {
    getResponse() {
      const path = "http://localhost:40011/home";
      fetch(path)
        .then((response) => response.text())
        .then((data) => (this.msg = data));
    },
  },
  created() {
    this.getResponse();
  },
};
</script>
