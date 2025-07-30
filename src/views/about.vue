<template>
    <el-space direction="vertical" size="large" class="mainBody">
        <div>
            <h1>{{ $t ('about.title1') }}</h1>
        </div>
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
                <font-awesome-icon icon="file-code" style="padding-right: 4px;"/>HTML  CSS   VUE
            </div>
            <h3><el-icon class="icons"><Platform /></el-icon>Back-End</h3>
            <div>
                <font-awesome-icon icon="database" style="padding-right: 4px;"/>SQL
                <font-awesome-icon icon="keyboard" style="padding-right: 4px;"/>C++, JAVA, Python, Swift, PHP
            </div>
            <h3><el-icon class="icons"><OfficeBuilding /></el-icon>General</h3>
            <div>Git, Cloud Computing, Enterprise-level Development, Agile Project Management</div>
            <h3><el-icon class="icons"><Hide /></el-icon>Not skilled but some basic</h3>
            <div>UE5, Unity, Maya</div>
        </div>
        <div>
            <el-slider v-model="value" :min="2018" :max="2024" :step="1" style="width: 300px" >
            </el-slider>
        </div>
        <div class="yearDoing">
            <div v-if="value===2018">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part2018') }}</p>
            </div> 
            <div v-if="value===2019">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part2019') }}</p>
            </div> 
            <div v-if="value===2020|| value===2021">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part2020To2021') }}</p>
            </div> 
            <div v-if="value===2022">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part2022') }}</p>
            </div> 
            <div v-if="value===2023">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part2023') }}</p>
            </div> 
            <div v-if="value===2024">
                <h2>{{ $t ('about.part3Title') }}</h2>   
                <p>{{ $t ('about.part3Content') }}</p>
            </div> 
        </div>

    </el-space>
    
</template>

<script setup>
import NaviBar from '../components/NaviBar.vue';
import footerOne from '../components/Footer.vue';
import resumeFile from '../assets/resume/CV.pdf';
import { faDatabase, faFileCode, faKeyboard } from '@fortawesome/free-solid-svg-icons';
import { library } from '@fortawesome/fontawesome-svg-core';
import { ref } from 'vue';
library.add( faDatabase, faKeyboard,faFileCode)

const value = ref('2018')

const download = ()=> {
    window.open(resumeFile)
}

</script>


<style scoped>
.mainBody {
    display: flex;
    left: 0%;
    margin-left: 10%;
    margin-right: 10%;
    animation: 1s ease-in fade-inL;

}


.timeline {
    height: 50px;
    display: flex;
    justify-content: center;
}

.icons {
    padding: 6px;
}

.yearDoing{
    animation: 1s ease-in fade-inL;
}

@keyframes fade-inL{
  0% {
    opacity: 0;
    transform: translateY(-30px);
  }
  70% {
    opacity: 0.5;
  }
  100%{
    opacity: 1;
    transform: translateY(0);
  }
}
</style>