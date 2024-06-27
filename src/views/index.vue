<template>
    <navi-bar></navi-bar>
    <div class="mainBody">
        <div class="part1 mb-4">
            <h2 class="mx-1">{{ $t ('home.title1') }}</h2>
            <h2>{{ $t ('home.title2') }}</h2>
            <el-button 
                 type="success"
                 @click="toAbout"
                round>
                {{ $t ('home.button1') }}
            </el-button>
        </div>
        <div class="part2">
            <h2>{{ $t ('home.part2Title1') }}</h2>
            <div>
                <el-text class="mb-1" style="padding-right: 20px;">{{ $t ('home.part2Content') }}</el-text>
                <el-button type="primary" round @click="toCurrentProject">
                    {{ $t ('home.button1') }}
                </el-button>
            </div>
        </div>
        <div class="ontheWay">
            <el-image src="src/assets/TestImage.jpg"></el-image>
        </div>
    </div>
    <el-backtop :right="100" :bottom="100" />
    <footerOne></footerOne>

</template>

<script setup>
import NaviBar from '../components/NaviBar.vue';
import footerOne from '../components/Footer.vue';
import { useRouter } from 'vue-router';
const router = useRouter()

const toAbout=() => {
    router.push('/about')
}
const toCurrentProject=() => {
    router.push('/current')
}


</script>

<style scoped>
.mainBody {
    margin-left: 7rem;
    margin-right: 7rem;
}

.part1 {
    display: block;
    margin: 8px;
    padding-bottom: 2rem;
}

.part2 {
    position: block;
    margin-left: 80%;
    width: 300px;
    padding: 10px;
}

.ontheWay {
    padding-top: 60px;
    justify-items: center;
    border-radius: 20px;
}

</style>
