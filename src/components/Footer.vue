<template>
  <div class="footer">
    <el-divider content-position="left">@Yuanle Yao 2024</el-divider>
    <div class="footer-content">
      <div class="left-footer">
        <span>
          {{ $t("footers.leftTitle1") }}
        </span>
        <span>
          {{ $t("footers.leftTitle2") }}
        </span>
      </div>
      <div class="right-footer">
        <el-link @click="centerDialogVisible = true">
          <el-icon><ChatDotRound /></el-icon>
          {{ $t("footers.contactWay1") }}: NClol12138
        </el-link>
        <span>
          <font-awesome-icon icon="envelope" />
          {{ $t("footers.contactWay2") }}: leoyao12138@gmail.com
        </span>
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
import { ref } from "vue";

const centerDialogVisible = ref(false);
</script>
    
<style scoped>
.footer {
  margin-top: 60px;
  bottom: 0%;
  width: 100%;
}

.footer-content {
  display: flex;
}

.left-footer {
  display: block;
  padding-left: 3rem;
  margin: 1rem;
}

.right-footer {
  margin: 3rem;
  position: absolute;
  right: 7rem;
}

.footer span {
  display: block;
  margin-bottom: 1rem;
}
</style>