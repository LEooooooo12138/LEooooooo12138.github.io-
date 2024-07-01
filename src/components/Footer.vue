<template>
  <div class="footer">
    <el-divider content-position="left">@Yuanle Yao 2024</el-divider>
    <div class="footer-content">
      <div class="left-footer">
        <div>
            <p>
              {{ $t("footers.leftTitle1") }}
            </p>
            <p>
              {{ $t("footers.leftTitle2") }}
            </p>
        </div>
        
      </div>
      <div class="right-footer">
        <div>
            <el-link @click="centerDialogVisible = true">
            <el-icon style="padding-right: 4px ;"><ChatDotRound /></el-icon>
              {{ $t("footers.contactWay1") }}: NClol12138
            </el-link>
        </div>
        <div>
          <el-link href="mailto:leoyao12138@gmail.com">
            <font-awesome-icon icon="envelope" style="padding-right: 4px;"/>
            {{ $t("footers.contactWay2") }}: leoyao12138@gmail.com
          </el-link>
        </div>

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
  display: flex;
  padding-left:5%;
  /* margin: 30px; */
}

.right-footer {
  margin: 10px;
  display: flex;
  flex-wrap: wrap;
  max-width: 300px;
  /* right: 7rem; */
}




</style>