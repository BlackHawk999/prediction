<template>
  <div class="quiz">
    <QuizBody v-if="step === 1">
      <div class="quiz-wrapper">
        <div class="quiz-title-wrapper">
          <h4 class="quiz__title title">Боитесь ли вы умереть?</h4>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--100"
            @click="step = 2"
          >
            Да
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--300"
            @click="step = 2"
          >
            Нет
          </button>
        </div>
      </div>
      <FooterView />
    </QuizBody>
    <QuizBody v-if="step === 2">
      <div class="quiz-top">
        <div class="quiz-top-wrapper">
          <p class="quiz-top__text text-bad">
            Мы расскажем Вам не только подробности вашей смерти, но также
            поможем Вам избежать этой ужасной даты и продлить вашу жизнь на
            многие годы.
          </p>
          <div class="quiz-top-img">
            <img src="@/assets/image/eye.png" alt="" />
          </div>
        </div>
      </div>
      <div class="quiz-wrapper">
        <div class="quiz-title-wrapper">
          <h4 class="quiz__title title">
            Когда Вы чувствуете себя наиболее комфортно?
          </h4>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--100"
            @click="step = 3"
          >
            Утро
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button class="quiz__button button-orange delay--300" @click="next">
            День
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--100"
            @click="step = 3"
          >
            Вечер
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--300"
            @click="step = 3"
          >
            Ночь
          </button>
        </div>
        <div class="quiz-img">
          <img src="@/assets/image/round.png" alt="" />
        </div>
      </div>
    </QuizBody>
    <QuizBody v-if="step === 3">
      <div class="quiz-top">
        <div class="quiz-top-wrapper">
          <p class="quiz-top__text text-bad">
            Мы расскажем Вам не только подробности вашей смерти, но также
            поможем Вам избежать этой ужасной даты и продлить вашу жизнь на
            многие годы.
          </p>
          <div class="quiz-top-img">
            <img src="@/assets/image/eye.png" alt="" />
          </div>
        </div>
      </div>
      <div class="quiz-wrapper">
        <div class="quiz-title-wrapper">
          <h4 class="quiz__title title">Укажите свою дату рождения:</h4>
        </div>
        <div class="quiz-input-wrapper">
          <input class="quiz__input" type="date" placeholder="Год" required />
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--300"
            @click="step = 4"
          >
            Далее
          </button>
        </div>
        <div class="quiz-img">
          <img src="@/assets/image/round.png" alt="" />
        </div>
      </div>
    </QuizBody>
    <QuizBody v-if="step === 4">
      <div class="quiz-top">
        <div class="quiz-top-wrapper">
          <p class="quiz-top__text text-bad">
            Мы расскажем Вам не только подробности вашей смерти, но также
            поможем Вам избежать этой ужасной даты и продлить вашу жизнь на
            многие годы.
          </p>
          <div class="quiz-top-img">
            <img src="@/assets/image/eye.png" alt="" />
          </div>
        </div>
      </div>
      <div class="quiz-wrapper">
        <div class="quiz-title-wrapper">
          <h4 class="quiz__title title">Снятся ли Вам умершие люди?</h4>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--100"
            @click="step = 5"
          >
            Да
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--300"
            @click="step = 5"
          >
            Нет
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--200"
            @click="step = 5"
          >
            Иногда
          </button>
        </div>
        <div class="quiz-img">
          <img src="@/assets/image/round.png" alt="" />
        </div>
      </div>
    </QuizBody>
    <QuizBody v-if="step === 5">
      <div class="quiz-top">
        <div class="quiz-top-wrapper">
          <p class="quiz-top__text text-bad">
            Мы расскажем Вам не только подробности вашей смерти, но также
            поможем Вам избежать этой ужасной даты и продлить вашу жизнь на
            многие годы.
          </p>
          <div class="quiz-top-img">
            <img src="@/assets/image/eye.png" alt="" />
          </div>
        </div>
      </div>
      <div class="quiz-wrapper">
        <div class="quiz-title-wrapper">
          <h4 class="quiz__title title">
            Запись, которую Вы услышите, может шокировать людей с неокрепшей
            психикой. Вы готовы узнать, что ждет именно Вас?
          </h4>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--100"
            @click="step = 6"
          >
            Да
          </button>
        </div>
        <div class="quiz-button-wrapper">
          <button
            class="quiz__button button-orange delay--300"
            @click="step = 6"
          >
            Затрудняюсь ответить
          </button>
        </div>
        <div class="quiz-img">
          <img src="@/assets/image/round.png" alt="" />
        </div>
      </div>
    </QuizBody>
    <p v-if="step < 6" class="quiz-text subtext">Вопрос {{ this.step }}-5</p>
    <QuizResult v-if="step === 6" @call="step = 7" />
    <ResultInfo v-if="step === 7" />
  </div>
</template>

<script>
import QuizBody from "@/components/quiz/QuizBody.vue";
import QuizResult from "@/components/quiz/QuizResult.vue";
import FooterView from "@/components/FooterView.vue";
import ResultInfo from "@/components/quiz/ResultInfo.vue";

export default {
  name: "quiz",
  components: {
    QuizBody,
    QuizResult,
    FooterView,
    ResultInfo,
  },

  data() {
    return {
      step: 1,
    };
  },
  methods: {
    next() {
      this.$emit = this.step;
    },
  },
};
</script>

<style lang="scss" scoped>
.quiz {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 50px 0;

  &-top {
    display: flex;
    justify-content: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);

    &-wrapper {
      position: relative;
      width: 60%;
      padding: 48px 0 37px 0;
    }

    &-img {
      position: absolute;
      width: 140px;
      height: 80px;
      right: 0;
      bottom: 0;

      img {
        width: 100%;
        height: 100%;
      }
    }
  }

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 35px;
  }

  &-title-wrapper {
    width: 60%;
    margin-top: 60px;

    h4 {
      width: 100%;
    }
  }

  &-button-wrapper {
    width: auto;
    max-width: 600px;
    min-width: 300px;
  }

  &-img {
    width: 89px;
    height: 89px;
    transform: translateX(-100%);
    img {
      width: 100%;
      height: 100%;
    }
  }

  &-text {
    margin-top: 36px;
  }

  &__input {
    font-family: Rob;
    font-size: 14px;
    padding: 25px 40px;
    border-radius: 50px;
    color: #202024;
    border: none;
    outline: none;
  }
}

@media screen and (max-width: 767.98px) {
  .quiz {
    &-top {
      &-wrapper {
        width: 100%;
        padding: 25px 5px 40px 5px;
      }

      &__text {
        font-size: 22px;
      }
    }
  }
}

@media screen and (max-width: 575.98px) {
  .quiz {
    &-top {
      &-wrapper {
        padding: 20px 40px;
      }

      &-img {
        width: 85px;
        height: 50px;
      }

      &__text {
        font-size: 14px;
      }
    }

    &-body {
      gap: 20px;

      &__title {
        font-size: 16px;
      }

      &-img {
        width: 52px;
        height: 52px;
      }

      &__button {
        font-size: 14px;
        padding: 20px 25px;
      }
    }
  }
}
</style>
