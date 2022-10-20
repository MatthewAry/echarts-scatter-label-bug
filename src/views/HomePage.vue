<template>
  <v-container class="home">
    <EChart />
  </v-container>
</template>

<script lang="ts">
import { defineComponent, ref, watch, type Ref, type SetupContext } from 'vue';
// import { useStore } from '@logue/vue2-helpers/vuex';
import { useRoute } from 'vue-router/composables';

import HelloWorld from '@/components/HelloWorld.vue';
import logo from '@/assets/vuetify.svg';
import EChart from '@/components/EChart.vue'

/** Home Component */
export default defineComponent({
  /** Components */
  components: {
    HelloWorld,
    EChart
  },
  /** Props */
  props: {
    prop: { type: String, default: 'prop' },
  },
  /**
   * Setup
   *
   * @param _props - Props
   * @param _context - Context
   */
  setup(_props, _context: SetupContext) {
    /** Route */
    const route = useRoute();
    /** Vuex */
    // const store = useStore();

    /** JSON LD sample */
    const jsonLd: Ref<string> = ref(
      JSON.stringify(
        {
          '@schema': 'https://json.schemastore.org/jsonld.json',
          '@context': 'http://schema.org',
          '@type': 'WebSite',
          name: 'Vite Vue2 TypeScript Startar',
          url: 'https://github.com/logue/vite-vue2-vuetify-ts-starter',
          description: 'Vite Vue2 TypeScript Demo Page',
          logo: logo,
        },
        null,
        2
      )
    );

    /* *
     * Computed
     * /
    const computedValue: Ref<string> = computed({
      get: () => store.getters.computedValue,
      set: v => store.dispatch('setComputedValue', v)
    }
     */

    // Watch
    watch(
      () => route?.name,
      name => console.log('route is changed:', name)
    );

    return {
      jsonLd,
    };
  },
});
</script>
