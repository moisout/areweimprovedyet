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
  { title: "Enable transpilation of JavaScript only without JAR generation", issue: 40 },
  { title: "Deploy in production", issue: 41 }
];
</script>

<template>
  <Html lang="en" />
  <main>
    <div class="github">
      <a href="https://github.com/jwanner83/liferay-npm-bundler-improved" rel="noreferrer noopener" target="_blank">
        <GithubLogo />
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
