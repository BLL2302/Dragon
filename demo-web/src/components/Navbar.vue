<template>
    <nav>
        <h1>This is nav</h1>
        <ul class="nav-link">
            <li><router-link to="/">Home</router-link></li>
            <li><router-link to="/About">Dark</router-link></li>
            <li><router-link to="/About">Weather</router-link></li>
            <li>i dont know</li>
        </ul>
    </nav>
</template>
<script>
export default {
    name:'Navbar'
}
</script>
<style scoped>
    nav{
        background-color: rgb(162, 23, 150);
        color: rgb(0, 0, 0);
        text-align: center;
        padding: 10px;
    }
    nav ul.nav-link {
        display:flex;
        justify-content:space-around ;
        list-style:none ;
        padding: 0;
        border: 1px solid #2e8b3c;
    }
    nav ul.nav-link :hover{
        color: azure;
    }
</style>
