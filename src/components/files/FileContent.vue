<template>
  <div>
    <el-row :gutter="20">
      <el-col :span="6">
        <div class="grid-content bg-purple">文件名</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">创建时间</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">最后修改</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">内容</div>
      </el-col>
    </el-row>
<!--    <div>111:{{files}}</div>-->
    <el-row :gutter="20" v-for="item in files" :key="item.id">
      <el-col :span="6">
        <div class="grid-content bg-purple">{{item.name}}</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">{{item.createdTime}}</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">{{item.modifiedTime}}</div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">{{item.content}}</div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  export default {
    name: 'FileContent',
    data () {
      return {
        // files: [{
        //   id: 1,
        //   name: 'a',
        //   createdTime: '2020-04-07 18:00:00',
        //   modifiedTime: '2020-04-07 18:00:01',
        //   content: 'abcd'
        // }]
        files: []
      }
    },
    mounted: function () {
      this.loadFiles()
    },
    methods: {
      loadFiles () {
        var _this = this
        var url = 'files/' + '1' + '/'
        this.$axios.get(url).then(resp => {
          if (resp && resp.data.code === 200) {
            _this.files = resp.data.result
          }
        })
      }
    }
  }

</script>

<style scoped>
  .cover {
    width: 115px;
    height: 172px;
    margin-bottom: 7px;
    overflow: hidden;
    cursor: pointer;
  }

  img {
    width: 115px;
    height: 172px;
    /*margin: 0 auto;*/
  }

  .title {
    font-size: 14px;
    text-align: left;
  }

  .author {
    color: #333;
    width: 102px;
    font-size: 13px;
    margin-bottom: 6px;
    text-align: left;
  }

  .abstract {
    display: block;
    line-height: 17px;
  }

  a {
    text-decoration: none;
  }

  a:link, a:visited, a:focus {
    color: #3377aa;
  }

</style>
