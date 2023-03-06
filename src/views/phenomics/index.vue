<template>
    <div class="phenomics-container">
      <el-drawer :visible="showDrawer" direction="ltr" :modal="false" :show-close="false">
        <div class="drawer-title" slot="title">
          <div>
            <span @click="closeDrawer()">
              <SvgIcon icon-class="angle-double-left" color="63C470" />
            </span>
            <span style="margin-left: 30px; color: #000;">Fliters</span>
          </div>
          <SvgIcon icon-class="refresh-left" color="000"></SvgIcon>
        </div>
        
      </el-drawer>
      <button @click="showDrawer = true">显示</button>
    </div>
</template>

<script>
import SvgIcon from '@/components/CommonComponents/SvgIcon.vue'
export default {
  components: { SvgIcon },
  data() {
    return {
      showDrawer: true
    }
  },
  methods: {
    closeDrawer() {
      this.showDrawer = false
    }
  }
}
</script>

<style scoped>
.drawer-title {
  display: flex;
  justify-content: space-between;
}
</style>