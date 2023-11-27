<template>
    <nav>
        <ul class="header">
            <li><router-link to ="/">Home</router-link></li>
            <li><router-link to="/about">About</router-link></li>
        </ul>
    </nav>
</template>

<script>
export default{

};
</script>

<style>
.header{
display: flex;
flex-direction: row;
gap: 1rem;
list-style-type: none;
}
.header li{
color: #222;
font-size: 20px;
font-family: poppins;
}
</style>