<template>
<div>
    {{reversedMessage}}
    {{numberer}}
    <button @click="resultMSG" class="btn">PushButton</button>
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
    reverseABC() {
      return this.reversedMessage.split('').reverse().join('');
    },
    numberDetermine() {
      return (this.numberer % 2) ? (-this.numberer) : this.numberer * 3;
    },
  },
  methods: {
    resultMSG() {
      this.$emit('resulter', this.numberDetermine, this.reverseABC);
    },

  },

};
</script>

<style>

</style>
