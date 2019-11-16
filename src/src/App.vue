<template>
  <div class="anim">
    <div class="mars item"></div>
    <div class="earth item"></div>
    <div class="venus item"></div>
    <div class="mercury item"></div>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 600 400">
      <g fill="none" fill-rule="evenodd" stroke-width="2">
         <circle class="mars_orbit" cx="300" cy="200" r="200" stroke="black" stroke-width="2" fill="white" />
         <circle class="earth_orbit" cx="300" cy="200" r="140" stroke="black" stroke-width="2" fill="white" />
         <circle class="venus_orbit" cx="300" cy="200" r="100" stroke="black" stroke-width="2" fill="white" />
         <circle class="mercury_orbit" cx="300" cy="200" r="80" stroke="black" stroke-width="2" fill="white" />
         <circle class="sun" cx="300" cy="200" r="40" stroke="black" stroke-width="2" fill="yellow" />
      </g>
    </svg>
  </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';

export default {
  name: 'app',
  components: {
  },
  mounted() {
    console.log("ssss");
    var mercury_pathEl = anime.path('.mercury_orbit');
    anime({
      targets: '.mercury',
      translateX: mercury_pathEl('x'),
      translateY: mercury_pathEl('y'),
      easing: 'linear',
      duration: 1500,
      loop: true
    });

    var venus_pathEl = anime.path('.venus_orbit');
    anime({
      targets: '.venus',
      translateX: venus_pathEl('x'),
      translateY: venus_pathEl('y'),
      easing: 'linear',
      duration: 2500,
      loop: true
    });

    var earth_pathEl = anime.path('.earth_orbit');
    anime({
      targets: '.earth',
      translateX: earth_pathEl('x'),
      translateY: earth_pathEl('y'),
      easing: 'linear',
      duration: 3000,
      loop: true
    });

    var mars_pathEl = anime.path('.mars_orbit');
    anime({
      targets: '.mars',
      translateX: mars_pathEl('x'),
      translateY: mars_pathEl('y'),
      easing: 'linear',
      duration: 3500,
      loop: true
    });

  }
  
}
</script>

<style>
    body {
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      overflow: hidden;
      width: 100%;
      height: 100%;
    }
    .anim, .anim svg {
      position: relative;
      width: 600px;
      height: 400px;
    }
    .anim path {
      stroke-width: 2;
    }
    .item {
      position: absolute;
      left: 0;
      top: 0;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      margin-left: -15px;
      margin-top: -15px;
      background-color: blue;
      z-index: 9999;
    }

    .mercury {
      background-color: silver;
    }

    .venus {
      background-color: brown;
    }
    .earth {
      background-color:blue;
    }
    .mars {
      background-color:gold;
    }

</style>
