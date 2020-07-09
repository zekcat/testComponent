<template>
<div>
    <button @click="getMessage" class="btn">{{name}}</button>
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
        this.$emit("clicked")
    }
}
}
</script>

<style scoped>
.btn{
    width: 100px;
    height: 40px;
    margin-top: 10px;
    background: white;
    border: solid 1px green;
}
</style>