<script setup>

</script>

<template>
  <router-view></router-view>
</template>


<style scoped>
body {
  background: #FAFAFA;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
/* .route-enter-from {
}
.route-enter-active {
    animation: fade-in 0.4s ease-in;
}
.route-enter-to {

}

@keyframes fade-in{
  0% {
    opacity: 0.5;
  }
  70% {
    opacity: 0.5;
  }
  100%{
    opacity: 1;
  }
} */
</style>
