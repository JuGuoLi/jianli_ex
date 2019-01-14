<template>
  <div>
     <div id='nav'>
       <div class='nav_container'>
         <a href="javascript:;">个人简历<span class='line'></span></a>
         <ul>
           <li><a href="javascript:;">首页</a></li>
           <li><a href="javascript:;">个人爱好</a></li>
           <li><a href="javascript:;">教育背景</a></li>
           <li><a href="javascript:;">项目</a></li>
           <li><a href="javascript:;">技能</a></li>
           <li><a href="javascript:;">所获奖项</a></li>
         </ul>
       </div>
     </div>
  </div>
</template>

<script>
  export default {
  }
</script>

<style scoped>
  #nav{
    width:100%;
    height:50px;
    margin-bottom:20px;
    padding:10px 0;
    background:rgb(25,25,25);
    opacity: .8;
    position:fixed;
    right:0;
    left:0;
    z-index:10;
  }
  .nav_container{
    width:970px;
    height:50px;
    padding-right:15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
  }
  .nav_container>a{
    float:left;
    text-decoration: none;
    color:white;
    font-family: 'Text Me One', sans-serif;
    font-size:34px;
    font-weight: bold;
    line-height:50px;
    transition:1s;
  }
  .nav_container>a:hover{
    color:red;
    
  }
  .nav_container .line{
    display:block;
    width:135px;
    height:10px;
    background:red;
    animation: linewidth 1s;
  }
  .nav_container ul{
    list-style: none;
    float:right;
    margin-right:-15px;
  }
  .nav_container ul li{
    float:left;
    position:relative;
    display: block;
    text-align: center;
  }
  .nav_container ul li a{
    color:#fff;
    font-size:24px;
    font-weight:normal;
    font-family: 'Text Me One', sans-serif;
    text-decoration:none;
    padding:0 10px;
    line-height:50px
  }
  @keyframes linewidth {
    0%{
      width:0px;
    }
    100%{
      width:135px;
    }
  }
</style>