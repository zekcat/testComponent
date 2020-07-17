<template>
  <div>
    <button @click="getMessage()" class="btn">{{name}}</button>
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
    };
  },
  computed: {
    somemethod3() {
      const mass = [];
      for (let i = 65; i <= 122; i += 1) {
        if (i < 91 || i > 96) {
          mass.push(i);
        }
      }
      return mass;
    },
  },
  methods: {
    getMessage() {
      let result;
      switch (this.actionChoose) {
        case 'randomNumber':
          result = Math.floor(Math.random() * 100) + 1;
          break;
        case 'Counter':
          this.count += 1;
          result = this.count;
          break;
        case 'randomABC':
          result = String.fromCharCode(this.somemethod3[
            Math.floor(Math.random() * this.somemethod3.length)]);
          break;
        default:
          break;
      }

      this.$emit('clicked', result);
    },
  },
};
</script>

<style scoped>
.btn {
  width: 100px;
  height: 40px;
  margin-top: 10px;
  background: white;
  border: solid 1px green;
}
</style>
