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
    },
    actionChoose:{
      type: String,
      default: "0",
    }
    
},
data() {
    return {
      count: 0,
      asciiKeys: [65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,
      85,86,87,88,89,90,97,98,99,100,101,102,103,104,105,106,107,108,109,110,111,
      112,113,114,115,116,117,118,119,120,121,122]
    }
  },
methods: {
    getMessage(){
        switch(this.actionChoose){
            case "0": alert((Math.floor(Math.random() * 100) + 1))
            break
            case "1": alert(++this.count)
            break
            case "2": alert(String.fromCharCode(this.asciiKeys[Math.floor(Math.random() *this.asciiKeys.length)]))
            break
        }
        

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