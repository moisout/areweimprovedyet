<script setup>
useHead({
  title: 'Are we improved yet?',
  meta: [
    {
      name: 'description',
      content: 'Is liferay-npm-bundler-improved ready for production?',
    },
  ],
  charset: 'utf-8',
});

const repoUrl = 'https://github.com/jwanner83/liferay-npm-bundler-improved';

const blockers = ref([
  { title: 'Allow Configuration', issue: 8 },
  { title: 'Enable bundling assets', issue: 39 },
  { title: 'Windows support', issue: 36 },
  {
    title: 'Enable transpilation of JavaScript only without JAR generation',
    issue: 40,
  },
  { title: 'Deploy in production', issue: 41 },
]);
</script>

<template>
  <Html lang="en" />
  <main>
    <div class="github">
      <a :href="repoUrl" rel="noreferrer noopener" target="_blank">
        <GithubLogo />
      </a>
    </div>
    <div class="center">
      <h1>{{ blockers.length ? 'No' : 'Yes' }}</h1>
      <div v-if="blockers.length" class="blockers">
        <h2>Blockers</h2>
        <ul>
          <li v-for="(blocker, id) in blockers" :key="id">
            {{ blocker.title }}
            <span v-if="blocker.issue">
              [<a
                :href="`${repoUrl}/issues/${blocker.issue}`"
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
#__nuxt,
main {
  margin: 0;
  height: 100%;
  width: 100%;
}
main {
  display: flex;
  font-family: Arial, Helvetica, sans-serif;

  .github {
    position: absolute;
    right: 0;
    margin: 20px;
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
