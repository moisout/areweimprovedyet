<script setup>
useHead({
  title: "Are we improved yet?",
  meta: [{ name: "description", content: "Is liferay-npm-bundler-improved ready for production?" }],
  charset: "utf-8"
});

const blockers = [
  { title: "Allow Configuration", issue: 8 },
  { title: "Enable bundling assets", issue: 39 },
  { title: "Windows support", issue: 36 },
  { title: "Enable transpilation of JavaScript only without JAR generation", issue: 40 }
];
</script>

<template>
  <Html lang="en" />
  <main>
    <div class="github">
      <a href="https://github.com/jwanner83/liferay-npm-bundler-improved" rel="noreferrer noopener" target="_blank">
        <svg
          height="32"
          aria-hidden="true"
          viewBox="0 0 16 16"
          version="1.1"
          width="32"
          data-view-component="true"
          class="octicon octicon-mark-github v-align-middle"
        >
          <path
            fill-rule="evenodd"
            d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
          ></path>
        </svg>
      </a>
    </div>
    <div class="center">
      <h1 v-if="blockers.length">No</h1>
      <h1 v-else>Yes</h1>
      <div v-if="blockers.length" class="blockers">
        <h2>Blockers</h2>
        <ul>
          <li v-for="(blocker, id) in blockers" :key="id">
            {{ blocker.title }}
            <span v-if="blocker.issue">
              [<a
                :href="`https://github.com/jwanner83/liferay-npm-bundler-improved/issues/${blocker.issue}`"
                rel="noreferrer noopener"
                target="_blank"
                >#{{ blocker.issue }}</a
              >]</span
            >
          </li>
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

  .github {
    position: absolute;
    top: 0;
    right: 0;
    padding: 20px;
  }

  .center {
    margin: auto;
    padding: 10px;

    h1 {
      font-size: 10rem;
      text-align: center;
    }

    h2 {
      font-size: 2rem;
    }

    li {
      font-size: 1.2rem;
    }
  }
}
</style>
