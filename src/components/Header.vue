<template>
    <div class="header">
        <div class="logo">
            <img src="@/assets/logo.png" alt="logo">
        </div>
        <nav>
            <router-link to="/">ABOUT US</router-link>
            <a href="#write-comment">WRITE COMMENT</a>
            <router-link to="/comments" class="active">COMMENTS</router-link>
        </nav>
        <router-view/>
    </div>
</template>


<script>
export default {
  name: 'Header'
}
</script>

<style>
.header {
    width: 100%;
    max-width: 1366px;
    padding: 50px;
    display: flex;
    justify-content: space-between;
    margin: auto;
    box-sizing: border-box;
    margin-bottom: 32px;
}
nav {
    display: flex;
    color: #111518;
    font-family: 'SofiaPro', sans-serif;
    font-size: 14px;
    font-weight: 600;
    line-height: 48px;
    text-transform: uppercase;
    justify-content: space-between;
    width: 100%;
    max-width: 364px;
    height: 11px;
}
nav a {
    text-decoration: none;
    color: #111518;
    position: relative;
}
nav a::after {
    background-color: #111518;
    content: "";
    position: absolute;
    width: 0%;
    height: 2px;
    bottom: -30px;
    left: 0;
    transition: width 0.3s ease-in-out;
}
nav a:hover::after {
    width: 100%;
}
.active::before {
    content: "";
    position: absolute;
    height: 2px;
    background-color: #f9d10d;
    width: 100%;
    left: 0;
    top: 0;
}
</style>
