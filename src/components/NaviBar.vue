<template>
  <div>
    <el-config-provider :locale="locale"> </el-config-provider>

    <el-menu
      :router="true"
      class="el-menu-demo"
      mode="horizontal"
      :ellipsis="false"
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
        <el-sub-menu index="/project">
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
</template>

<script lang="ts" setup>
import { computed, ref } from "vue";
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
  locale.value = localStorage.getItem("language");
};
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