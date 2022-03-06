<template>
  <div class="footer">
    <div class="container">
      <div class="footer-wrapper">
        <div class="footer-icon-wrapper">
          <img src="@/assets/image/footer-icon.png" alt="" />
        </div>
        <p class="footer-top__text text-bad">
          Вы, конечно, умрете. <br />
          И все, с кем вы знакомы, <br />
          тоже однажды умрут.
        </p>
        <div class="footer-icon-wrapper">
          <img src="@/assets/image/footer-icon-2.png" alt="" />
        </div>
        <div class="footer-background-right">
          <img src="@/assets/image/eye.png" alt="" />
        </div>
        <div class="footer-background-left">
          <img src="@/assets/image/round.png" alt="" />
        </div>
        <div class="footer-text-wrapper">
          <p class="footer__text">
            TERMENI SI CONDITII: ACESTA ESTE UN SERVICIU DE <br />
            DIVERTISMENT. PRIN FOLOSIREA LUI DECLARATI CA AVETI 18 ANI
            IMPLINITI,
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "footerview",
};
</script>

<style lang="scss" scoped>
.footer {
  position: relative;
  width: 100%;
  padding: 50px 0 0 0;
  overflow: hidden;

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &-top__text {
    margin: 60px 0 40px 0;
  }

  &-icon-wrapper {
    display: flex;
    justify-content: center;
  }

  &-background-right {
    position: absolute;
    top: 0;
    right: 0;
    width: 296px;
    height: 170px;

    img {
      width: 100%;
      height: 100%;
    }
  }

  &-background-left {
    position: absolute;
    width: 164px;
    height: 164px;
    left: 0;
    bottom: 0;

    img {
      width: 100%;
      height: 100%;
    }
  }

  &-text-wrapper {
    display: flex;
    justify-content: center;
    margin-top: 52px;
  }

  &__text {
    font-family: Rob;
    font-size: 12px;
    line-height: 18px;
    color: #9d9d9d;
    text-transform: uppercase;
    text-align: center;
  }
}

@media screen and (max-width: 991.98px) {
  .footer {
    &-background-right {
      width: 200px;
      height: 110px;
      transform: translateX(40%);
    }
    &-background-left {
      width: 110px;
      height: 110px;
      transform: translateX(-50%);
    }
  }
}

@media screen and (max-width: 767.98px) {
  .footer {
    &__text {
      margin: 40px 0;
    }

    &-background-right {
      width: 170px;
      height: 100px;
      right: 0;
      top: 20%;
    }

    &-background-left {
      width: 100px;
      height: 100px;
      left: 0;
      bottom: 20%;
    }
  }
}

@media screen and (max-width: 575.98px) {
  .footer {
    &__text {
      padding: 0 30px;
    }

    &-background-right {
      width: 100px;
      height: 70px;
      right: 0;
      top: 10%;
    }
    &-background-left {
      width: 52px;
      height: 52px;
      left: 0;
      bottom: 20%;
    }
  }
}
</style>
