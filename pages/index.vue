<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        component-learn
      </h1>
      <h2 class="subtitle">
        hrllo
      </h2>
      <div class="links">
          <Bbutton name="Random Number" @clicked="alertMsg"/>
          <Bbutton actionChoose="randomABC" name="Random ABC" @clicked="alertMsg"/>
          <Bbutton actionChoose="Counter" name="Counter" @clicked="alertMsg"/>
      </div>
      <br/>
      <hr/>
      <h1>Task2</h1>
      <input v-model="someText" type="text" placeholder="Введите текст"/>
      <input v-model="number" type="number" placeholder="Введите число"/>
      <p>Введенное сообщение : {{ someText }}</p>
      <p>Введенное число = {{number}}</p>
      <Reactiv :reversedMessage= "someText" :numberer= "number"
       @resulter="newNumber"  @resulter2="newZnach" />

    </div>
  </section>
</template>

<script>
import AppLogo from '../components/AppLogo.vue';
import Reactiv from '../components/ReactiveReverse.vue';
import Bbutton from '../components/ComponentButton.vue';

export default {
  components: {
    AppLogo,
    Bbutton,
    Reactiv,
  },
  data() {
    return {
      someText: '',
      number: null,
    };
  },
  methods: {
    alertMsg(text) {
      alert(text);
    },
    newZnach(reversedMessage) {
      this.someText = reversedMessage;
    },
    newNumber(numberer) {
      this.number = numberer;
    },
  },
};

</script>
<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro",
  -apple-system, BlinkMacSystemFont,
   "Segoe UI", Roboto, "Helvetica Neue",
    Arial, sans-serif; /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
