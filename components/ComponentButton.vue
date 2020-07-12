<template>
   <div >
    <button @click="getMessage" class="btn">{{name}}</button>
   </div>
</template>

<script>
export default {

  props: {
    name: {
      type: String,
      required: true,
    },
    actionChoose: {
      type: String,
      default: 'randomNumber',
    },

  },
  data() {
    return {
      count: 0,
      asciiKeys: [],
      init: true,
    };
  },

  methods: {
    getMessage() {
      switch (this.actionChoose) {
        case 'randomNumber': this.$emit('clicked', (Math.floor(Math.random() * 100) + 1));
          break;
        case 'Counter':
          this.$emit('clicked', this.count += 1);
          break;
        case 'randomABC':
          if (this.init) {
            this.initArray();
          }
          this.$emit('clicked', String.fromCharCode(this.asciiKeys[
            Math.floor(Math.random() * this.asciiKeys.length)]));
          break;
        default:
          break;
      }
    },
    initArray() {
      for (let i = 65; i <= 122; i += 1) {
        if (i < 91 || i > 96) {
          this.asciiKeys.push(i);
        }
      }
      this.init = false;
    },
  },
};
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
