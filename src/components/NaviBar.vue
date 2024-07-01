<template>
  <div v-if="!isMobile">
    <el-config-provider :locale="locale"> </el-config-provider>
    <el-menu
      :router="true"
      class="el-menu-poper-demo"
      mode="horizontal"
      ellipsis
      :popper-offset="6"
    >
      <el-menu-item index="/">
        <el-icon><house /></el-icon>
        <p>{{ $t("nav.home") }}</p>
      </el-menu-item>
      <div class="flex-grow">
        <el-menu-item index="/about">
          <font-awesome-icon icon="user" style="padding-right: 8px" />
          {{ $t("nav.about") }}
        </el-menu-item>
        <el-sub-menu index="/project" disabled="true">
          <template #title
            ><Edit
              style="
                width: 1em;
                height: 1em;
                margin-right: 8px;
                font-size: 20px;
              "
            />{{ $t("nav.myProj") }}</template
          >
          <el-menu-item index="/current">{{ $t("nav.current") }}</el-menu-item>
          <el-menu-item index="/past">{{ $t("nav.past") }}</el-menu-item>
        </el-sub-menu>
        <el-menu-item index="/contact">
          <font-awesome-icon icon="phone" style="padding-right: 8px" />
          {{ $t("nav.contact") }}
        </el-menu-item>
        <el-menu-item @click="toggle">
          <el-button type="success" circle>
            <font-awesome-icon icon="language" size="xl" />
          </el-button>
        </el-menu-item>
      </div>
    </el-menu>
  </div>

  <div v-else>
    我是移动端的navbae\r

  </div>
</template>

<script lang="ts" setup>
import { width } from "@fortawesome/free-brands-svg-icons/fa42Group";
import { fa } from "element-plus/es/locales.mjs";
import { computed, onBeforeUnmount, onMounted, ref } from "vue";
import { useI18n } from "vue-i18n";
const { locale } = useI18n();

const activeIndex = ref("/");
const handleSelect = (key: string, keyPath: string[]) => {
  console.log(key, keyPath);
};

const toggle = () => {
  const language = localStorage.getItem("language");
  if (language) {
    const str = language === "zh" ? "en" : "zh";
    localStorage.setItem("language", str);
  } else {
    localStorage.setItem("language", "zh");
  }
  locale.value = localStorage.getItem("language") || "zh";
};


//=================
const isMobile = ref(false)
onMounted(()=>{
    checkMobile();
    // 监听窗口大小变化
    window.addEventListener('resize', checkMobile);
})
onBeforeUnmount(()=>{
  window.removeEventListener('resize', this.checkMobile);
})
const checkMobile = ()=>{
  const val = /iPhone|iPad|iPod|Android/i.test(navigator.userAgent);
  
  isMobile.value = val;
}


</script>


<style>
.flex-grow {
  display: flex;
  justify-content: right;
  flex-grow: 1;
}

.el-menu-demo {
  padding-right: 1rem;
}
</style>