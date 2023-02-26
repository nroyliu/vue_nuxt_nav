<template>
  <div>
    <div>
      {{this.$route.params.cate == undefined}}
      <NuxtLink to="/" exact>category</NuxtLink>
      <NuxtLink to="/cate1">category 1</NuxtLink>
      <NuxtLink to="/cate2">category 2</NuxtLink>
      <NuxtLink to="/cate3">category 3</NuxtLink>
      <NuxtLink to="/cate4">category 4</NuxtLink>
    </div>
    <div style="width: 1024px; margin: 0 auto">
      <el-row :gutter="5" style="background: aliceblue">
        <el-col :span="24"><div class="grid-content bg-purple" style="height: 100px"></div></el-col>
      </el-row>

      <div>
        <Nuxt/>
      </div>
      <div style="background: antiquewhite">

        <el-row :gutter="5">

          <el-col :span="17">
                  <el-row style="background: bisque">
                    <el-col :span="24" v-for="item in 10"><div class="grid-content bg-purple"></div></el-col>
                  </el-row>
          </el-col>
          <el-col :span="7">
                    <el-row style="background: bisque">
            <el-col :span="24" v-for="item in 8"><div class="grid-content bg-purple" style="height: 60px"></div></el-col>
                    </el-row>
          </el-col>
          <!--      <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>-->
        </el-row>
      </div>
    </div>
<!--    <div v-for="item in 100">{{item}}</div>-->
  </div>
</template>

<script>
export default {
  name: "_cate",
  mounted() {
    console.log(this.$route.params)
    console.log(this.$route.params.cate)
  }
}
</script>

<style scoped>
.el-row {
  margin-bottom: 20px;
  &:last-child {
     margin-bottom: 0;
   }
}

.el-col {
  margin-bottom: 20px;
&:last-child {
   margin-bottom: 0;
  background: blue;
 }
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
</style>
