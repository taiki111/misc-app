<template>
  <div class="form-container">
    <input v-model="inputingDescription" />
    <button
      class="save-button"
      @click="$emit('post-tweet', inputingDescription)"
    >
      post
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const inputingDescription = ref<string>("");

    return {
      inputingDescription,
    };
  },
});
</script>

<style scoped>
.form-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: aliceblue;
  padding: 24px 0;
  width: 60%;
  margin-bottom: 12px;
  border-radius: 4px;
}

.save-button {
  color: #fff;
  font-weight: bold;
  background-color: #68c9c9;
  border-radius: 2px;
  border: none;
  width: 60px;
  height: 22px;
  margin-top: 12px;
}

.save-button:hover {
  background-color: #37bdbd;
}
</style>
