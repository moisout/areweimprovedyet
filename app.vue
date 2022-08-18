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

const blockers = ref([]);
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
      <div class="blockers">
        <a
          href="https://clavisit-wiki.atlassian.net/wiki/spaces/WS/blog/2022/08/18/3757703622/liferay-npm-bundler-improved+-+Let+s+Go"
          >Check the blog post!</a
        >
      </div>
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
