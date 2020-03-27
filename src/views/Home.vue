<template>
  <div class="home">
    <el-form ref="formInline" :inline="true" :model="formInline" class="demo-form-inline">
      <el-form-item label="demo1" prop="user">
        <el-input v-model="formInline.user" placeholder="请输入" />
      </el-form-item>
      <el-form-item label="demo2" prop="content">
        <el-input v-model="formInline.content" placeholder="请输入" />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit('formInline')">查询</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data() {
    return {
      formInline: {
        user: '',
        content: ''
      }
    }
  },
  methods: {
    onSubmit(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          alert('submit!')
        } else {
          console.log('error submit!!')
          return false
        }
      })
    }
  }

}
</script>
