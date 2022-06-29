<template>
<div>
    <div class="webheader" id="weblogo">
        <router-link to="/"><h2>LLWEB</h2></router-link>
    </div>
    <h1 class="webheader" id="webmss">
        Welcome to 1st web made by BLL
    </h1>
    </div>
</template>

<script>
export default {
    name:'Header-web'
}
</script>
<style>
.webheader{
  display: flex;
  justify-content: center;
  text-align: center; 

}
#weblogo{
    background-image: url(../assets/icelogo.png) ;
    height: 120px;
    width: 160px;
    float: left;
    justify-content: center;
    text-align: center; 
}
#webmss{

    height: 120px;
    width: auto;
    justify-content: center;
    text-align: center; 

}

</style>