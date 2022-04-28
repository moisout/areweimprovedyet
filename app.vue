<script setup>
useHead({
  title: "Are we improved yet?"
});
const versions = useState("vers-1", () => process.versions);
onMounted(() => {
  console.log(versions.value);
});
</script>

<template>
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
  font-family: "sans-serif";

  .center {
    margin: auto;
    h1 {
      font-size: 10rem;
    }
  }
}
</style>
