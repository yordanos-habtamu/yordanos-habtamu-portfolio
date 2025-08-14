<template>
    <div class="divider"></div>
</template>
<style scoped>
.divider{
   position:relative;
   height:70px;
   background:black;
}

.divider::before{
    content:"";
    position:absolute;
    /* top:0px; */
    bottom:0px;
    width:100%;
    height:70px;
    background:whitesmoke;
    border-radius:  0  0 100% 100% ;}
</style>  