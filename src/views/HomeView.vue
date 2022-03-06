<template>
  <div class="home">
    <Intro />
    <Prediction />
    <Quiz />
    <FooterView />
  </div>
</template>

<script>
import Intro from "@/components/Intro.vue";
import Prediction from "@/components/Prediction.vue";
import Quiz from "@/components/quiz/Quiz.vue";
import FooterView from "@/components/FooterView.vue";

export default {
  name: "HomeView",

  components: {
    Intro,
    Prediction,
    Quiz,
    FooterView,
  },
};
</script>

<style lang="scss">
.home {
  background: #202024;
}
</style>
