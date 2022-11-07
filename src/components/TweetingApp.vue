<template>
  <div class="container">
    <h1>Tweeter</h1>
    <TweetPostForm @post-tweet="postTweet" />

    <div class="tweet-container">
      <p v-show="tweets.length <= 0">No tweets have been added</p>
      <ul>
        <TweetList :tweets="tweets" @delete-tweet="deleteTweet" />
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import TweetPostForm from "@/components/TweetPostForm.vue";
import TweetList from "@/components/TweetList.vue";

export default defineComponent({
  name: "TweetingApp",
  components: {
    TweetPostForm,
    TweetList,
  },

  setup() {
    const tweets = ref([
      {
        id: 0,
        description: "Hello World",
      },
      {
        id: 1,
        description: "this is the second tweet",
      },
    ]);
    const inputingDescription = ref<string>("");

    const postTweet = (description: string) => {
      const tweet = {
        id: Math.random(),
        description: description,
      };
      tweets.value.push(tweet);
    };

    const deleteTweet = (id: number) => {
      tweets.value = tweets.value.filter((t) => t.id !== id);
    };

    return {
      tweets,
      inputingDescription,
      postTweet,
      deleteTweet,
    };
  },
});
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  margin-bottom: 16px;
}
</style>
