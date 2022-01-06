<template>
  <section class="circles-wrapper">
    <div class="circles">
      <div v-for="i in 75" :key="i"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Circles',
  methods: {
    testingCircles: function() {
      const circlesEl = document.getElementsByClassName('circles-wrapper')[0];
      const interval = 1000;
      const initialValue = 500;

      setTimeout( function() {
        circlesEl.classList.add('grey');
      }, initialValue + interval * 0);

      setTimeout( function() {
        circlesEl.classList.add('lavander');
      }, initialValue + interval * 1);

      setTimeout( function() {
        circlesEl.classList.add('orange');
      }, initialValue + interval * 2);

      setTimeout( function() {
        circlesEl.classList.remove('grey');
        circlesEl.classList.remove('lavander');
        circlesEl.classList.remove('orange');
      }, initialValue + interval * 3);
    },
    changeBorderColorOnClick: function() {
      // const circlesEl = document.getElementsByClassName('circles')[0];
      const bodyEl = document.getElementById('app');

      bodyEl.addEventListener("mouseover", (event) => {
        // const xPosition = event.clientX;
        // const yPosition = event.clientY;
        // const r = 255;
        // const g = 255;
        // const b = 255;
        // const rSum = r - xPosition * .1;
        // const gSum = g - yPosition * .05;
        // const bSum = b - xPosition * .025 + yPosition * .025;
        // const max = 255;
        // const min = 0;

        console.log(event.target.classList)

        // if (rSum <= max && gSum <= max && bSum >= min) {
        //   event.target.style.borderColor = `rgba(${rSum}, ${gSum}, ${bSum}, 0.5)`;
        //   console.log(rSum, gSum, bSum);
        // } else {
        //   console.log(rSum, gSum, bSum);
        // }

        // event.target.style.borderColor = `rgba(0, 0, 0, 0.5)`;
        event.target.classList.add('grey')

        // circlesEl.style.borderColor = `rgba(${r}, ${g}, ${b}, 0.2)`;

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

