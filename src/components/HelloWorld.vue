<template>
  <div>...</div>
</template>

<script lang="ts">
import gql from 'graphql-tag';
import { Component, Vue } from 'vue-property-decorator';

@Component({
  apollo: {
    language: {
      manual: true,
      query: gql`{ ... }`,
      variables() {
        return {
          language: this.language,
        };
      },
      result({ data, loading }: { data: any, loading: any }) {
        this.result = data;
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

  result!: any;
}
</script>
