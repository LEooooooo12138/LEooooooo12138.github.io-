<template>
    <navi-bar></navi-bar>
    <div class="mainBody">
        <h2>{{ $t ('current.title1') }} {{ $t ('current.projectName') }}</h2>
        <p>I am working on this page now. 我他妈在写呢别催了</p>
    </div>
    
    
    
    <footerOne></footerOne>
</template>

<script setup>
import NaviBar from '../components/NaviBar.vue';
import footerOne from '../components/Footer.vue';
</script>

<style scoped>
.mainBody {
  margin-left: 10%;
  margin-right: 10%;
}

</style>