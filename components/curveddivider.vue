<template>
    <div class="divider"></div>
</template>
<style scoped>
.divider{
   position:relative;
   height:70px;
   background:white;
}

.divider::before{
    content:"";
    position:absolute;
    bottom:0px;
    width:100%;
    height:50px;
    background:whitesmoke;
    border-radius: 100% 100% 0 0;
}
</style>  