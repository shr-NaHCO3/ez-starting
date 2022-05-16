<template>
  <div class="select-box">
    <input type="text" id="select" class="select" placeholder="搜索"/>
    <div class="fab-sites">
      <fabSiteCard />
    </div>
  </div>  
</template>

<script>
import fabSiteCard from "./components/fabSiteCard.vue"

export default {
  name: 'App',
  components: {
    fabSiteCard
  }
}
</script>

<style>
.select-box{
  display: flex;
  flex-direction: column;
  justify-content: center; /* 水平居中 */
  align-items: center;     /* 垂直居中 */

  height: 100%;
}
.select{
  width: 514px;
  height: 40px;
  outline-style: none;
  border-radius: 20px;
  text-align: center;
  font-size: 15px;

  background-color: #454545;
  transition: all .2s cubic-bezier(0.075, 0.82, 0.165, 1);
}
.select:hover{
  background-color: #d4d4d4;
}
.select:focus{
  background-color: #ffffff;
  box-shadow: 0px 0px 7px #454545;
}

/* 书签栏 */
.fab-sites{
  width: 514px;
  padding-top: 24px;
  height: 254px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
