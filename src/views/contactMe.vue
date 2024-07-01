<template>
    <navi-bar></navi-bar>
    <div class="mainBody">
        <h1>Contact Me</h1>

        <h2>If you are interested in me, please contact me</h2>
        <div>
            <p>Phone: +61 0466556933</p>
            <div class="right-footer">
                <el-link @click="centerDialogVisible = true">
                <el-icon><ChatDotRound /></el-icon>
                    {{ $t("footers.contactWay1") }}: NClol12138
                </el-link>
                <br/>
                <el-link href="mailto:leoyao12138@gmail.com">
                <font-awesome-icon icon="envelope" />
                    {{ $t("footers.contactWay2") }}: leoyao12138@gmail.com
                </el-link>
            </div>
        </div>
    </div>

    <footerOne></footerOne>


    <el-dialog
    v-model="centerDialogVisible"
    title="Scan This QR code to Add Me"
    width="500"
    center
  >
    <el-image
      style="width: 450px; height: 500px"
      src="src/assets/weChatQRCode.jpg"
      fit="contain"
    ></el-image>
    <template #footer>
      <div class="dialog-footer">
        <el-button @click="centerDialogVisible = false">
            {{ $t("footers.cencel") }}</el-button>
        <el-button type="primary" @click="centerDialogVisible = false">
          {{ $t("footers.yes") }}
        </el-button>
      </div>
    </template>
  </el-dialog>
</template>

<script setup>
import NaviBar from '../components/NaviBar.vue';
import footerOne from '../components/Footer.vue';

import { ref } from "vue";

const centerDialogVisible = ref(false);
</script>

<style scoped>
.mainBody {
    margin-left: 10%;
    margin-right: 10%;

}
</style>