<template>
  <div class="record">
    <div class="record-wrapper">
      <div class="record-img">
        <img src="@/assets/image/record.png" alt="" />
      </div>
      <div class="record-input-wrapper">
        <input class="record__input" type="range" readonly />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "record",
};
</script>

<style lang="scss" scoped>
.record {
  &-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  &-input-wrapper {
    input[type="range"] {
      -webkit-appearance: none;
      outline: none;
      overflow: hidden;
      width: auto;
      max-width: 500px;
      min-width: 300px;
      height: 10px;
      border-radius: 30px;
      box-shadow: inset 1px 1px 5px 2px silver;
    }
    input[type="range"]:hover::-webkit-slider-thumb {
      background: #f6c866;
      box-shadow: -500px 0 0 500px #f6c866;
    }
    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      cursor: pointer;
      width: 10px;
      height: 10px;
      background: #f6c866;
      border-right: 6px solid #f6c866;
      box-shadow: -500px 0 0 500px #f6c866;
    }
  }
}
</style>
