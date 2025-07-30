<template>
    <div class="mainBody">
        <h1>{{ $t ('contact.title') }}</h1>

        <h2>{{ $t ('contact.label')}}</h2>
        <div>
            <p>{{ $t ('contact.phone')}}</p>
            <br/>
            <div class="right-footer">
                <el-link @click="centerDialogVisible = true">
                <el-icon><ChatDotRound /></el-icon>
                    {{ $t("footers.contactWay1") }}: NClol12138
                </el-link>
                <br/>
                <br/>
                <el-link href="mailto:leoyao12138@gmail.com">
                <font-awesome-icon icon="envelope" />
                    {{ $t("footers.contactWay2") }}: leoyao12138@gmail.com
                </el-link>
            </div>
        </div>
    </div>


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