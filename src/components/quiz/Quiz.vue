<template>
  <div class="quiz">
    <div class="container">
      <div class="quiz-wrapper">
        <QuizBody v-if="step === 1">
          <div class="quiz-element-wrapper">
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
        </QuizBody>
        <QuizBody v-if="step === 2">
          <div class="quiz-top">
            <div class="quiz-top-wrapper">
              <p class="quiz-top__text text-bad">
                Мы расскажем Вам не только подробности вашей смерти, но также
                поможем Вам избежать этой ужасной даты и продлить вашу жизнь на
                многие годы.
              </p>
            </div>
          </div>
          <div class="quiz-element-wrapper">
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
              <button
                class="quiz__button button-orange delay--300"
                @click="step = 3"
              >
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
            </div>
          </div>
          <div class="quiz-element-wrapper">
            <div class="quiz-title-wrapper">
              <h4 class="quiz__title title">Укажите свою дату рождения:</h4>
            </div>
            <div class="quiz-input-wrapper">
              <input
                class="quiz__input"
                type="date"
                placeholder="Год"
                required
                v-model="birthdate"
              />
            </div>
            <div class="quiz-button-wrapper">
              <button
                class="quiz__button button-orange delay--300"
                @click="fetchInfo"
              >
                Далее
              </button>
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
            </div>
          </div>
          <div class="quiz-element-wrapper">
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
          </div>
        </QuizBody>
        <QuizBody v-if="step === 5">
          <div class="quiz-top">
            <div class="quiz-top-wrapper">
              <div class="quiz-feedback">
                <p
                  class="quiz__text text-bad"
                  v-if="dateDiffInYears >= 18 && dateDiffInYears <= 35"
                >
                  По вам скучает очень близкий человек, которого больше нет в
                  мире живых.
                </p>
                <p
                  class="quiz__text text-bad"
                  v-else-if="dateDiffInYears <= 36 && dateDiffInYears <= 45"
                >
                  По вам скучает очень близкий человек, которого больше нет в
                  мире живых. Возможно это дедушка или бабушка.
                </p>
                <p class="quiz__text text-bad" v-else>
                  По вам скучает очень близкий человек, которого больше нет в
                  мире живых. Возможно это кто-то из Ваших родителей.
                </p>
              </div>
            </div>
          </div>
          <div class="quiz-element-wrapper">
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
          </div>
        </QuizBody>
        <p v-if="step < 6" class="quiz-text subtext">
          Вопрос {{ this.step }}-5
        </p>
        <Record v-if="step === 6"/>
        <QuizResult v-if="step === 7" @call="step = 7" />
        <ResultInfo v-if="step === 8" />
      </div>
      <Loader v-if="loading" />
    </div>
  </div>
</template>

<script>
import QuizBody from "@/components/quiz/QuizBody.vue";
import QuizResult from "@/components/quiz/QuizResult.vue";
import ResultInfo from "@/components/quiz/ResultInfo.vue";
import Loader from "@/components/Loader.vue";
import Record from "@/components/quiz/Record.vue";

export default {
  name: "quiz",
  components: {
    QuizBody,
    QuizResult,
    ResultInfo,
    Loader,
    Record,
  },

  data() {
    return {
      step: 1,
      birthdate: "",
      loading: false,
    };
  },
  computed: {
    dateDiffInYears() {
      const birthday = new Date(this.birthdate);
      const ageDifMs = Date.now() - birthday;
      const ageDate = new Date(ageDifMs);
      return Math.abs(ageDate.getUTCFullYear() - 1970);
    },
  },
  methods: {
    next() {
      this.$emit = this.step;
    },

    fetchInfo() {
      this.loading = true;

      setTimeout(() => {
        this.step = 4;
        this.loading = false;
      }, 3000);
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

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &-top {
    display: flex;
    justify-content: center;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);

    &-wrapper {
      position: relative;
      width: 80%;
      padding: 48px 0 35px 0;
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

  &-feedback {
    position: relative;
    padding: 6px 14px;
    background: #ffffff;
    border-radius: 5px;

    &::after {
      position: absolute;
      content: "";
      width: 0;
      height: 0;
      right: 20px;
      border-left: 15px solid transparent;
      border-right: 15px solid transparent;
      border-top: 20px solid #ffffff;
    }
  }

  &__text {
    color: #202024;
  }

  &-element-wrapper {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 35px;
  }

  &-title-wrapper {
    width: 80%;
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
    position: absolute;
    width: 89px;
    height: 89px;
    left: 0;
    bottom: 0;
    transform: translateY(100%);

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
    width: auto;
    max-width: 600px;
    min-width: 300px;
    padding: 25px 30px;
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
        padding: 25px 10px;
      }

      &__text {
        font-size: 22px;
      }
    }

    &-title-wrapper {
      margin-top: 36px;
    }
  }
}

@media screen and (max-width: 575.98px) {
  .quiz {
    &-top {
      &-wrapper {
        padding: 20px 20px;
      }

      &-img {
        width: 85px;
        height: 50px;
      }

      &__text {
        font-size: 14px;
      }
    }

    &__text {
      font-size: 14px;
    }

    &-wrapper {
      gap: 20px;
    }

    &-title-wrapper {
      margin-top: 36px;
    }

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
</style>
