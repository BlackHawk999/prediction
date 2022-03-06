<template>
  <div class="loader">
    <div class="loader-wrapper">
      <div class="loader-img">
        <img src="@/assets/image/loader.svg" alt="" />
      </div>
      <p class="loader__text">Loading...</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "loader",
};
</script>

<style lang="scss" scoped>
.loader {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 100;
  background: #202024;

  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &-img {
    width: 300px;
    height: 300px;

    img {
      width: 100%;
      height: 100%;
      object-fit: contain;
    }
  }

  &__text {
    font-family: Rob;
    font-size: 14px;
    font-weight: 300;
    color: rgba(255, 255, 255, 0.6);
  }
}
</style>
