<template>
  <div class="home">
    <TweetingApp />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TweetingApp from "@/components/TweetingApp.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    TweetingApp,
  },
});
</script>
