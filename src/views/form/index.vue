<template>
  <div class="app-container" style="width:80%; margin-left:10%;">
    <h1>不动产登记工作人员培训学时认定系统</h1>
    <h2>不动产登记工作人员注册</h2>
    <el-form ref="form" :model="form" :rules="rules"  label-width="150px">
      <el-form-item label="姓名" prop="name">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="身份证号">
        <el-input v-model="form.id_code"></el-input>
      </el-form-item>
      <el-form-item label="工作单位">
        <el-input v-model="form.org_name"></el-input>
      </el-form-item>
      <el-form-item label="手机">
          <el-input v-model="form.mobile"></el-input>
      </el-form-item>
      <el-form-item label="电子邮件">
          <el-input v-model="form.email"></el-input>
      </el-form-item>
      <el-form-item label="性别">
        <el-select v-model="form.sex" placeholder="请选择">
          <el-option 
          v-for="item in form.sex_sel"
          :key="item.value"
          :label="item.label"
          :value="item.value">
          </el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="民族">
          <el-input v-model="form.nation"></el-input>
      </el-form-item>
      <el-form-item label="学历">
          <el-input v-model="form.education"></el-input>
      </el-form-item>
      <el-form-item label="首次上岗单位">
          <el-input v-model="form.first_org_name"></el-input>
      </el-form-item>
      <el-form-item label="首次上岗时间">
          <el-date-picker type="date" placeholder="请选择日期" v-model="form.first_org_date" style="width: 100%;"></el-date-picker>
      </el-form-item>
      <el-form-item label="从事登记工作年限">
          <el-input v-model="form.name"></el-input>
      </el-form-item>      
      
      <el-form-item>
        <el-button type="primary" @click="onSubmit">注册</el-button>
        <el-button @click="onCancel">清空</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        id_code: "",
        org_name: "",
        mobile: "",
        email: "",
        sex: "",
        nation: "",
        email: "",
        education: "",
        first_org_name: "",
        first_org_date: "",
        age_limit: "",
        sex_sel: [{ value: "1", label: "男" }, { value: "0", label: "女" }]
      },
      rules: {
        name: [{ required: true, message: "姓名不能为空", trigger: "blur" }]
      }
    };
  },

  methods: {
    onSubmit() {
      this.$refs["form"].validate(valid => {
        if (valid) {
          this.$message("submit!");
        } else {
          console.log("error submit!!");
          return false;
        }
      });
    },
    onCancel() {
      this.$message({
        message: "cancel!",
        type: "warning"
      });
    }
  }
};
</script>

<style scoped>
.line {
  text-align: center;
}
</style>
