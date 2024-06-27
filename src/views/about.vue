<template>
    <navi-bar></navi-bar>
    <el-space direction="vertical" size="large" class="mainBody">
        <h1>{{ $t ('about.title1') }}</h1>
        <el-button @click="download">{{ $t ('about.getResume') }}</el-button>
        <div>
            <h2>{{ $t ('about.part1Title') }}</h2>
            <p> {{ $t ('about.part1Content') }}</p>
        </div>
        
        <div>
            <h2>{{ $t ('about.part2Title') }}</h2>   
            <p>{{ $t ('about.part2Content') }}</p>
        </div>

        <div>
            <h3><el-icon class="icons"><Monitor /></el-icon>Front-End</h3>
            <div>
                HTML,CSS, VUE
            </div>
            <h3><el-icon class="icons"><Platform /></el-icon>Back-End</h3>
            <div>SQL, C++, JAVA, Python, Swift, PHP</div>
            <h3><el-icon class="icons"><OfficeBuilding /></el-icon>乱七八糟</h3>
            <div>git, cloud computing, enterprise-level development, Agile Project Management</div>
            <h3><el-icon class="icons"><Hide /></el-icon>Not skilled but some basic</h3>
            <div>UE5, Unity, Maya</div>
        </div>

    </el-space>
    

    <footerOne></footerOne>
</template>

<script setup>
import NaviBar from '../components/NaviBar.vue';
import footerOne from '../components/Footer.vue';
import resumeFile from '../assets/resume/CV.pdf'

const download = ()=> {
    window.open({resumeFile})
}
</script>


<style scoped>
.mainBody {
    margin-left: 7rem;
    margin-right: 7rem;
}

.icons {
    padding: 6px;
}
</style>