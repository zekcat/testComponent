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
        <a
          href="../components/testPage1.vue"
          target="_blank"
          class="button--green">Testing Page1</a>
        <a
          href="~/testFile.vue"
          target="_blank"
          class="button--grey">Testing Page2</a>
          <Bbutton name="Random Number"/>
          <Bbutton actionChoose="randomABC" name="Random ABC"/>
          <Bbutton actionChoose="Counter" name="Counter"/>
      </div>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import Bbutton from '../components/ComponentButton.vue'

export default {
  components: {
    AppLogo,
    Bbutton,
  }
}

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
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
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

