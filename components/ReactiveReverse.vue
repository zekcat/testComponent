<template>
<div>
  <p>Из дочернего элемента {{reversedMessage}}</p>
  <p>Число из дочернего элемента = {{numberer}}</p>
    <button @click="returnData" class="btn">PushButton</button>
    <hr/>
    <br/>
    <p>Inputs дочернего элемента</p>
    <input type="text"  v-bind:="setInput()"
    @input="reversedMessage=$event.target.value" placeholder="Введите текст">
    <input type="number" v-bind:="setNumber()" @input="setNumber" placeholder="Введите число">
</div>
</template>

<script>
export default {
  props: {
    reversedMessage: {
      type: String,
      required: true,
    },
    numberer: {
      type: Number,
      required: true,
    },

  },
  computed: {
    setInput22() {
      return this.$emit('resulter2', this.reversedMessage);
    },
  },
  methods: {
    returnData() {
      this.$emit('resulter', this.numberDetermine());
      this.$emit('resulter2', this.reverseABC());
    },
    reverseABC() {
      return this.reversedMessage.split('').reverse().join('');
    },
    numberDetermine() {
      return (this.numberer % 2) ? (-this.numberer) : this.numberer * 3;
    },
    setInput() {
      this.$emit('resulter2', this.reversedMessage);
    },
    setNumber() {
      this.$emit('resulter', this.numberer);
    },

  },

};
</script>
<style>

</style>
