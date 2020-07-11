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
          href="../components/testPage1.vue"
          target="_blank"
          class="button--grey">Testing Page2</a>
          <Bbutton name="Random Number"/>
          <Bbutton actionChoose="2" name="Random ABC"/>
          <Bbutton actionChoose="1" name="Counter"/>
      </div>
    </div>
  </section>
</template>