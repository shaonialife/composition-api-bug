<template>
  <div class="hello">
    {{ msg }}
  </div>
</template>

<script>
import Vue from 'vue';
import { onMounted } from '@vue/composition-api';

// use Vue.extend
export default Vue.extend({
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  mixins: [
    {
      // normal
      mounted() {
        console.log('mixin1 mounted');
      },
    },

    {
      // called twice when re-create
      setup() {
        onMounted(() => {
          console.log('mixin2 onMounted');
        });
      },
    },
  ],

  setup() {
    onMounted(() => {
      console.log('onMounted');
    });
  },
});
</script>
