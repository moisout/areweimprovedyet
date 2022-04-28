<script setup>
useHead({
  title: "Are we improved yet?",
  meta: [{ name: "description", content: "Is liferay-npm-bundler-improved ready for production?" }],
  charset: "utf-8"
});
</script>

<template>
  <Html lang="en" />
  <main>
    <div class="center">
      <h1>No</h1>
      <div class="blockers">
        <h2>Blockers</h2>
        <ul>
          <li>lnbs-copy-assets: Bundle assets with liferay-npm-bundler-improved</li>
          <li>
            Configuration support [<a href="https://github.com/jwanner83/liferay-npm-bundler-improved/issues/8">#8</a>]
          </li>
          <li>
            Windows support [<a href="https://github.com/jwanner83/liferay-npm-bundler-improved/issues/36">#36</a>]
          </li>
          <li>Use liferay-npm-bundler-improved without jar generation</li>
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
  font-family: sans-serif, "Arial";

  .center {
    margin: auto;
    h1 {
      font-size: 10rem;
    }
  }
}
</style>
