<template>
  <div v-if="post.jobApplyEmail" class="job-entry-cta">
    <a :href="`mailto:${post.jobApplyEmail}`">
      <factor-btn btn="primary">
        Apply Now
        <factor-icon icon="fas fa-arrow-right" />
      </factor-btn>
    </a>
  </div>
</template>
<script lang="ts">
import { factorBtn, factorIcon } from "@factor/ui"
import { stored } from "@factor/api"

export default {
  components: { factorBtn, factorIcon },
  props: {
    postId: { type: String, default: "" },
  },
  computed: {
    post(this: any) {
      return stored(this.postId) || {}
    },
  },
}
</script>

<style lang="less">
.plugin-jobs.careers {
  .single-entry {
    .job-entry-cta {
      margin: 3em auto;
      @media (max-width: 767px) {
        padding: 0 2em;
      }
    }
  }
}
</style>
