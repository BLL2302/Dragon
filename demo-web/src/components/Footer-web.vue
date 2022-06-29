<template>
<div class="webfooter">
    <ul id="menu">
        <li><a href="#">Menu 1</a>
            <ul id="sub">             
                <li><a href="#">Sub Menu 1</a></li>
                <li><a href="#">Sub Menu 2</a></li>
                <li><a href="#">Sub Menu 3</a></li>
                <li><a href="#">Sub Menu 4</a></li>
                <li><a href="#">Sub Menu 4</a></li>
            </ul>
        </li>
        <li><a href="#">Menu 2</a>
            <ul id="sub">             
                <li><a href="#">Sub Menu 1</a></li>
                <li><a href="#">Sub Menu 2</a></li>
                <li><a href="#">Sub Menu 3</a></li>
                <li><a href="#">Sub Menu 4</a></li>
            </ul>
        </li>
        <li><a href="#">Menu 3</a>
            <ul id="sub">             
                <li><a href="#">Sub Menu 1</a></li>
                <li><a href="#">Sub Menu 2</a></li>
                <li><a href="#">Sub Menu 3</a></li>
            </ul>
        </li>
        <li><a href="#">Menu 4</a>
            <ul id="sub">             
                <li><a href="#">Sub Menu 1</a></li>
                <li><a href="#">Sub Menu 2</a></li>
                <li><a href="#">Sub Menu 3</a></li>
            </ul>
        </li>
        <li><a href="#">Menu 5</a>
            <ul id="sub">             
                <li><a href="#">Sub Menu 1</a></li>
                <li><a href="#">Sub Menu 2</a></li>
                <li><a href="#">Sub Menu 3</a></li>
            </ul>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name:'Footer-web'
}
</script>

<style>
.webfooter{

    height: 200px;
    width: auto;
}
#menu{
    display: flex;
}
ul#menu, ul#menu ul#sub {
    padding:0;
    margin: 0;
}
ul#menu li {
     list-style-type: none;    /* code này để bỏ các dấu chấm tròn*/
     float: left;    /* code này để menu dàn hàng ngang*/
     margin-right: 10px;    /* tạo lề cho các menu*/
}
ul#menu li a {
text-decoration: none;
background-color: #900;
padding: 5px;
color: white;
}
ul#menu li {
position: relative;
}
ul#menu li ul#sub {
display: none;
position: absolute;
width: 100px;
}
ul#menu li ul#sub li {
margin-top: 10px;
margin-bottom: 5px;
}
ul#menu li:hover ul#sub {
display: block;
}
</style>
