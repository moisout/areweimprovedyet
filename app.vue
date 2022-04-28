<script setup>
useHead({
  title: "Are we improved yet?"
});
</script>

<template>
  <main>
    <div class="center">
      <h1>No</h1>
      <div class="blockers">
        <h2>Blockers</h2>
        <ul>
          <li>
            Windows support [<a href="https://github.com/jwanner83/liferay-npm-bundler-improved/issues/36">#36</a>]
          </li>
          <li>JSP gradle build support</li>
        </ul>
      </div>
    </div>
  </main>
</template>

<style lang="scss">
html,
body,
#__nuxt {
  margin: 0;
  height: 100%;
  width: 100%;
}
main {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  font-family: "sans-serif";

  .center {
    margin: auto;
    h1 {
      font-size: 10rem;
    }
  }
}
</style>
