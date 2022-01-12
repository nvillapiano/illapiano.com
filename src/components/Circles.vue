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
    changeBorderColorOnHover: function() {
      const bodyEl = document.getElementById('app');
      const colorClass = 'color';
      bodyEl.addEventListener("mouseout", (event) => {
        event.target.classList.add(colorClass)
        setTimeout(() => {
          event.target.classList.remove(colorClass)
        }, 300);
      }, false);
    },
    sizeAndPositionShapes: function() {

      // Selectors
      const circlesParent = document.getElementsByClassName('circles')[0];
      const circlesChildren = circlesParent.childNodes;

      // Constant values
      const zBase= 1;
      const initialPositionValue= .55;
      const initialSizeValue= .6;

      // Sizing and positioning
      for (let i = 0; i < circlesChildren.length; i++) {

        const positionOffset =  initialPositionValue * i;
        const dimensionOffset = 100 - (initialSizeValue * i);
        const zOffset = zBase + i;

        circlesChildren[i].style.top = `${positionOffset}%`;
        circlesChildren[i].style.left = `${positionOffset}%`;
        circlesChildren[i].style.width = `${dimensionOffset}%`;
        circlesChildren[i].style.height = `${dimensionOffset}%`;
        circlesChildren[i].style.zIndex = zOffset;
      }
    },
    squares: function() {
      const circlesEl = document.getElementsByClassName('circles')[0];
      const squareClass = 'square';
      const square2Class = 'square2';
      const circle2Class = 'circle2';
      const burstClass = 'burst';
      const rotateClass = 'rotate';

      circlesEl.addEventListener('click', () => {

        // end/reset
        if (circlesEl.classList.contains(burstClass)) {
          circlesEl.classList.remove(squareClass);
          circlesEl.classList.remove(square2Class);
          circlesEl.classList.remove(circle2Class);
          circlesEl.classList.remove(burstClass);
        }
        // step 2
        else if (circlesEl.classList.contains(squareClass)) {
          circlesEl.classList.remove(squareClass);
          circlesEl.classList.add(square2Class);
        }
        // step 3
        else if (circlesEl.classList.contains(square2Class)) {
          circlesEl.classList.remove(squareClass);
          circlesEl.classList.remove(square2Class);
          circlesEl.classList.add(circle2Class);
        }
        // step 4
        else if (circlesEl.classList.contains(circle2Class)) {
          circlesEl.classList.remove(squareClass);
          circlesEl.classList.remove(square2Class);
          circlesEl.classList.remove(circle2Class);
          // start color burst
          setTimeout(() => {
            circlesEl.classList.add(burstClass);
          }, 50);
          // remove color burst
          setTimeout(() => {
            circlesEl.classList.remove(burstClass);
          }, 800);
        }
        // step 1
        else {
          circlesEl.classList.add(squareClass);
        }
      }, false);
    },
  },
  mounted() {
    // this.changeBorderColorOnHover();
    this.sizeAndPositionShapes();
    this.squares();

  },
}
</script>

<style lang="scss">

</style>

