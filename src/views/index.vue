<template>
  <!-- <el-skeleton animated loading/> -->
  <div class="mainBody">
    <div class="part1 mb-4">
        <div style="margin-top: 25px;">
            <h2 class="mx-1">{{ $t("home.title1") }}</h2>
            <h3>{{ $t("home.title2") }}</h3>
            <el-button type="success" @click="toAbout" round>
              {{ $t("home.button1") }}
            </el-button>
        </div>
            <el-image
            src="src/assets/person1.png"
            style="width: 30%; height: 30%; padding-top: 50px;"
            :fit="contain"
          ></el-image>

    </div>
    <div class="part2">
      <div>
        <h3>{{ $t("home.part2Title1") }}</h3>
        <div>
          <el-text class="mb-4" style="padding-right: 20px">{{
            $t("home.part2Content")
          }}</el-text>
          <el-button type="primary" round @click="toCurrentProject">
            {{ $t("home.button1") }}
          </el-button>
        </div>
      </div>
    </div>
  </div>
  <div class="ontheWay">
      {{ $t("home.stillWork") }}
  </div>
  <el-backtop :right="100" :bottom="100" />
</template>

<script setup>
import { useRouter } from "vue-router";
const router = useRouter();

const toAbout = () => {
  router.push("/about");
};
const toCurrentProject = () => {
  router.push("/current");
};
</script>

<style scoped>
.mainBody {
  margin-left: 10%;
  margin-right: 10%;

  animation: 1s ease-in fade-inL;
}

.part1 {
  display: flex;
  justify-content: space-between;
  width: 100%;
}


.part2 {
  width: 100%;
  display: flex;
  justify-content: end;
  padding: 10px;
}

.ontheWay {
  border: 1px solid #ddd;
  box-shadow: 5px 5px rgba(155, 155, 155, 0.741);
  border-radius: 50px;
  width: 100%;
  height: 200px;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  padding-top: 15%;
  font-size: 25px;
  text-shadow: 1px 1px rgba(72, 79, 72, 0.696);
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
