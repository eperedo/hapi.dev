<template>
  <div class="changelog-wrapper">
    <h2 class="changelog-header">
      <a id="changelog" href="#changelog" class="anchor" aria-hidden="true"></a>Changelog
    </h2>
    <ChangelogVersion
      v-for="change in milestones"
      v-bind:key="change[0].id"
      :version="change[0].milestone.title"
      :versionUrl="change[0].milestone.html_url"
      :issues="change"
    />
  </div>
</template>

<script>
import ChangelogVersion from './ChangelogVersion.vue';
export default {
  components: {
    ChangelogVersion
  },
  props: ['milestones']
};
</script>

<style lang="scss">
@import '../../assets/styles/main.scss';

.changelog-wrapper {
  width: 100%;
  padding: 20px 100px 10px 100px;
}

.changelog-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

@media screen and (max-width: 1500px) {
  .changelog-wrapper {
    padding: 20px 40px;
  }
}

@media screen and (max-width: 900px) {
  .changelog-wrapper {
    padding: 0;
  }
}
</style>
