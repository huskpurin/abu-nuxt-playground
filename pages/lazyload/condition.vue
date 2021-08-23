<template>
  <div>
    <h1>condition</h1>
    <!-- 2. by if/for or other vue conditions-->
    <!-- https://nuxtjs.org/blog/improve-your-developer-experience-with-nuxt-components#lazy-loading-your-components -->
    <nav>
      <button
        v-for="tab in tabs"
        v-bind:key="tab"
        v-bind:style="tab === currentTab && `color: yellow; font-weight: bold;`"
        v-on:click="currentTab = tab"
      >
        {{ tab }}
      </button>
    </nav>
    <component v-bind:is="currentTabComponent" class="tab"></component>
  </div>
</template>
<script>
const CompA = () => import('@/components/test/A.vue');
const CompB = () => import('@/components/test/B.vue');
const CompC = () => import('@/components/test/C.vue');

export default {
  data: function () {
    return {
      currentTab: 'A',
      tabs: ['A', 'B', 'C']
    };
  },
  computed: {
    currentTabComponent: function () {
      const currentTab = this.currentTab;
      const compMap = {
        A: CompA,
        B: CompB,
        C: CompC
      };

      return compMap[currentTab] || compMap.A;
    }
  }
};
</script>
