<template>
  <div>
    <div class="nav" :class="{'nav-hidden': top > 500}">
      <ul>
        <li v-for="item in list">
          <NuxtLink :to="item.url">{{ item.name }}</NuxtLink>
        </li>
      </ul>
    </div>
    <div class="nav-span"></div>
    <Nuxt/>
  </div>
</template>

<script>
export default {
  name: "default",
  data() {
    return {
      top: 0,
      list: [
        {
          "name": "首页",
          "url": "/"
        },
        {
          "name": "页面1",
          "url": "/page1"
        },
        {
          "name": "页面2",
          "url": "/page2"
        },
      ]
    }
  },
  mounted() {
    const _this = this
    window.addEventListener("scroll", function (e){
      // console.log(document.documentElement.scrollTop)
      _this.top = document.documentElement.scrollTop;
    })
  }
}
</script>

<style scoped>
.nav {
  background: aliceblue;
  /*padding: 20px 0;*/
  position: fixed;
  width: 100%;
  transition: linear .1s;
}
.nav ul {
  list-style: none;
}
.nav ul li {
  float: left;
}
.nav-span {
  height: 62.5px;
}
.nav-hidden {
  margin-top: -62.5px;
}
</style>
