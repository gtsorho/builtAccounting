<template>
    <div >
        <router-view></router-view>
    </div>
</template>

<style lang="scss">
        @import url('https://fonts.googleapis.com/css2?family=Raleway&display=swap');
        html,body, p, h1,h2,h4,h5,h6{
            font-family: 'Raleway', sans-serif !important;
        }
        body,html{
            background-color: #ffffff !important;  
        }
        
        $primary: #0561be;
        $secondary: #bbbbbb;

      @import "../node_modules/bootstrap/scss/bootstrap";
</style>