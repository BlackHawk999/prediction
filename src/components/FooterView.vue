<template>
  <div class="footer">
    <div class="container">
      <div class="footer-wrapper">
        <div class="footer-icon-wrapper">
          <img src="@/assets/image/footer-icon.png" alt="" />
        </div>
        <p class="footer__text text-bad">
          Вы, конечно, умрете. И все, с кем вы знакомы, тоже однажды умрут.
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

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__text {
    max-width: 400px;
    margin: 80px 0 40px 0;
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
    transform: translate(-100%, 60%);

    img {
      width: 100%;
      height: 100%;
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
      transform: translateX(50%);
    }
    &-background-left {
      width: 80px;
      height: 80px;
      left: -30%;
      bottom: 0%;
    }
  }
}

@media screen and (max-width: 575.98px) {
  .footer {
    &__text {
      padding: 0 30px;
    }

    &-background-right {
      width: 85px;
      height: 50px;
      right: 0;
      top: 20%;
    }
    &-background-left {
      width: 52px;
      height: 52px;
      left: 10%;
      bottom: 0%;
    }
  }
}
</style>
