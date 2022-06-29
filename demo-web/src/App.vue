<template>
  <div id="app1">
    <div id="webtop" class="fullscreen">
      <header> <headerweb/> </header>
      <Navbar/>
      <h1 id="Navtitle">Hello App!</h1>
      <p id="routertest">
        <router-link to="/">Go to Home</router-link>
        <router-link to="/about">Go to About</router-link>
      </p>
    </div>
    <div id="webmain" class="fullscreen">
      <div class="menumain" id="menuleft">
        <h1>Menu left</h1>

      </div>
      <div class="menumain" id="menuright">
        <h1>menu right</h1>
      </div>

      <div class="routerweb">
        <router-view></router-view>
      </div>
    </div>
    <footer id="lowbottom"> <Footerweb/></footer>
  </div>


</template>
<script>
import Navbar from './components/Navbar.vue'
import Footerweb from './components/Footer-web.vue'
import headerweb from './components/header-web.vue'
export default{
  name:'app',
  components:{
    Navbar,
    Footerweb,
    headerweb,
}
}
</script>

<style>

#app1{
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab, #228dd5,#9a3ce7);
  background-size: 400% 400%;
  animation: gradient 20s ease infinite;
  height: 100%;
  width: 100%;
}
#app1 {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 2rem;
  }
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  25% {
    background-position: 0% 25%;
  }
  50% {
    background-position: 100% 50%;
  }
  75% {
    background-position: 70% 25%;
  }
  100% {
    background-position: 0% 50%;
  }}
footer{
  text-align: center;
  height: 80px;
}
.fullscreen{
  display: flex;
  justify-items: center;
  flex-direction: column;
}
#Natititle{
  display: flex;
  text-align: center;

}
#routertest{
  display: flex;
  text-align: center;
  justify-content: space-around ;
  text-decoration: none ;
}
#lowbottom{
  display: flex;
  align-items: flex-start;
  justify-content: space-around ;
}
#webmain {
    border: 1px solid red;
}
#webmain {
  display: flex;

}
#menuleft {
    background: #f3f3cf;
    flex: 20%;
    justify-content: flex-end;

}

#menuright {
    background: #e0e0fc;
    flex: 20%;
    justify-content: flex-start;

}

.routerweb {
    
    flex: 60%;
    justify-content: center;

}

</style>
