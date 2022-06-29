<template>
<div id="Location-world">
  <h1>Seach Location</h1>
    <div class="mid">
        <input type="text" v-model="name_location" placeholder=" Enter location "/>
        <button v-on:click="Seaching">Seach</button>
        <button v-on:click="isshow = !isshow && name_location == location_name ">See weather per hour</button>
        <button v-on:click="dasshow = !dasshow && name_location == location_name ">See weather next day</button>
    </div>
  <h2 v-show="normalshow=!normalshow && name_location == location_name " >  Weather now : {{ weather_now }} </h2>
        <table class ="Location-detailshow" id="by-hours" v-show="isshow" >
            <thead>
               <tr>
                  <td>Weather_hours</td>
                  <td>Time_hours</td>
                </tr>
              
            </thead>
            <tbody>
               <tr v-for="data in datas" :key="data.condition.text">
                <th> {{data.condition.text}} </th>
                <th> {{data.time.split(' ')[1]}} </th>
              </tr>
            </tbody>
        </table>
        <table class ="Location-detailshow" id="by-days" v-show="dasshow" >
            <thead>
               <tr>
                  <td>Weather_days</td>
                  <td>Days</td>
                </tr>
              
            </thead>
            <tbody>
               <tr v-for="data in days " :key="data.day.condition.text">
                <th> {{data.day.condition.text}} </th>
                <th> {{data.date.split('-')[2]}} </th>
              </tr>
            </tbody>
        </table>
        
</div>
</template>

<script>
import axios from 'axios';
export default {
  name :'Location-world',
  data(){
    return{
      normalshow : false,
      dasshow : false,
      isshow : false,
      name_location : null,
      location_name: null,
      weather_now: null,
      //day_date : null,
      datas : [],
      days : []

    }
  },
  methods:{
    Seaching (){
      axios
      .get('http://api.weatherapi.com/v1/forecast.json?key=b8c9d08fd4574e739bf70228222505&q=London&days=10&aqi=no&alerts=no')
      .then(response => (
        // this.world = response,
        this.location_name = response.data.location.name,
        this.weather_now = response.data.current.condition.text,
        // this.day_date = response.data.current.last_updated,
        this.datas = response.data.forecast.forecastday[1].hour,
        this.days = response.data.forecast.forecastday
        ))
      .catch(error => console.log(error))
      }
  },
}



</script>

<style scoped>
/*div{
  background-image: url("../assets/weather_bg.png") ;
      height: 600px;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
} */
#Location-world{
  height: 100%;
  width: 100%;
}
.mid input{
    width: 200px;
    height: 80px;
    padding-left: 20px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 2px solid rgb(255, 0, 0);
}
.mid button{
    height: 50px;
    width: 100px;
    background-color: aqua;
    border: 1px solid rgb(200, 41, 24);
    cursor: pointer;
    display:inline-flex;
    justify-content: space-around ;
}
div h2 {
  width: 80pm;
  color: blue;
}
.Location-detailshow {
  display: block;
}
#by-hours {
  width: 300px;
  margin: auto;
  padding: 10px;
  float:left;
  border: 1px solid red;
}
#by-days {
  margin: auto;
  padding: 10px;
  width: 300px ;
  float:right;
  border: 1px solid red;
}
table, th, td {
  border: 1px solid;
}


</style>
