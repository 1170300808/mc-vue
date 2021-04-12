<template>
  <el-container>
    <el-aside style="width: 200px;margin-top: 20px">
      <switch></switch>
      <SideMenu></SideMenu>
    </el-aside>
    <el-main>
      <FileContent class="file_content"></FileContent>
    </el-main>
  </el-container>
</template>

<script>
  import SideMenu from './SideMenu'
  import FileContent from './FileContent'

  export default {
    name: 'FileIndex',
    components: {SideMenu, FileContent}
  }
</script>

<style scoped>
  .file_content {
    margin-left: 50px;
  }
</style>
