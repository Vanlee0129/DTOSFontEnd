<template>
    <div class="dyxq">
        <el-container>
            <el-card class="box-card">
                <div class="head">定义箱区</div>
                <div class="content">
                    <div class="xqs">箱区数：</div>
                    <el-input v-model="input1" placeholder="请输入箱区数"></el-input>
                    <div class="xqs">最大排数：</div>
                    <el-input v-model="input2" placeholder="请输入最大排数"></el-input>
                    <div class="xqs">最大贝位数：</div>
                    <el-input v-model="input3" placeholder="请输入最大贝位数"></el-input>
                    <div class="xqs">最大层数：</div>
                    <el-input v-model="input4" placeholder="请输入最大层数"></el-input>
                </div>
                <div class="submit">
                    <el-button>提交</el-button>
                </div>
            </el-card>
        </el-container>
    </div>
</template>

<style>
.box-card {
  width: 100%;
  height: 500px;
  font-size: 24px;
  font-weight: bold;
  margin-left: 50px;
}

.content{
    display: inline-block;
    text-align: justify;
}

.xqs {
  position: relative;
  top: 33px;
  left: -145px;
}

.submit{
    margin-top: 24px;
}

</style>

<script>
export default {
  name: "dyxq",
  data() {
    return {
      input1: "",
      input2: "",
      input3: "",
      input4: ""
    };
  }
};
</script>
