<template>
  <section class="circles-wrapper">
    <div class="circles">
      <div v-for="i in 69" :key="i"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Circles',
  methods: {
    changeBorderColorOnClick: function() {
      const bodyEl = document.getElementById('app');
      bodyEl.addEventListener("mouseout", (event) => {
        event.target.classList.add('grey')
        setTimeout(() => {
          event.target.classList.remove('grey')
        }, 300);
      }, false);
    }
  },
  mounted() {
    this.changeBorderColorOnClick();
  },
}
</script>

<style lang="scss">

</style>

