<template>
  <TrackList v-if="items" :tracks="items" />
</template>
<script lang="ts">
  import Vue from 'vue'
  import TrackList from '@/library/TrackList.vue'

  export default Vue.extend({
    components: {
      TrackList,
    },
    data() {
      return {
        items: null as any,
      }
    },
    created() {
      this.$api.getStarred().then(result => {
        this.items = result
      })
    }
  })
</script>
