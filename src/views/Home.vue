<template>
  <Circles />
</template>

<script>
// @ is an alias to /src
import Circles from "@/components/Circles.vue";

export default {
  name: "home",
  components: {
    Circles,
  },
  methods: {
    consoleInfo: function() {
      console.log(" ___   ___      ___      _______");
      console.log("|   | |   |    |   |    |   _   |");
      console.log("|   | |   |    |   |    |  |_|  |");
      console.log("|   | |   |    |   |    |       |");
      console.log("|   | |   |___ |   |___ |       |");
      console.log("|   | |       ||       ||   _   |");
      console.log("|___| |_______||_______||__| |__|");
      console.log(" _______  ___   _______  __    _  _______");
      console.log("|       ||   | |   _   ||  |  | ||       |");
      console.log("|    _  ||   | |  |_|  ||   |_| ||   _   |");
      console.log("|   |_| ||   | |       ||       ||  | |  |");
      console.log("|    ___||   | |       ||  _    ||  |_|  |");
      console.log("|   |    |   | |   _   || | |   ||       |");
      console.log("|___|    |___| |__| |__||_|  |__||_______|");
      console.log("Let's make something cool together");
      console.log("nickv@illapiano.com");
      console.log("--------------------------------");
      console.log("https://www.doitlewitt.com");
      console.log("https://citymonsturz.netlify.app/");
    },
  },
  mounted() {
    this.consoleInfo();
  },
};
</script>
