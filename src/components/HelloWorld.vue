<template>
  <div>...</div>
</template>

<script lang="ts">
import gql from 'graphql-tag';
import { Component, Vue } from 'vue-property-decorator';

@Component({
  apollo: {
    language: {
      query: gql`{ ... }`,
      variables() {
        return {
          language: this.language,
        };
      },
      error() {
        this.error = true;
      },
      watchLoading(isLoading) {
        this.loading = isLoading;
      },
    },
  },
})
export default class HelloWorld extends Vue {
  language = 'fr';
  error = false;
  loading = false;
}
</script>
