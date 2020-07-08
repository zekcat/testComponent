<template>
<div>
    <button @click="getMessage" class="btn-color">{{name}}</button>
</div>
</template>

<script>
export default {
props: {
    name:{
      type: String,
      required: String,
    }
    
},
methods: {
    getMessage(){
        this.$emit("alerter")
    }
}
}
</script>

<style scoped>
.btn-color{
    width: 100px;
    height: 40px;
    margin-top: 10px;
    background: white;
    border: solid 1px green;
}
</style>