<template>
  <div class="result-info">
    <table class="result-info__table">
      <tr>
        <th>Name</th>
        <th>Height</th>
        <th>Mass</th>
        <th>Hair color</th>
        <th>Skin color</th>
        <th>Eye color</th>
        <th>Birth year</th>
        <th>Gender</th>
        <th>Homeworld</th>
        <th>Films</th>
      </tr>
      <tr>
        <td>{{ info.name }}</td>
        <td>{{ info.height }}</td>
        <td>{{ info.mass }}</td>
        <td>{{ info.hair_color }}</td>
        <td>{{ info.skin_color }}</td>
        <td>{{ info.eye_color }}</td>
        <td>{{ info.birth_year }}</td>
        <td>{{ info.gender }}</td>
        <td>{{ info.homeworld }}</td>
        <td>{{info.films[0]}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "resultinfo",
  computed: {
    ...mapState({
      info: (state) => state.user,
    }),
  },
};
</script>

<style lang="scss" scoped>
.result-info {
  overflow-x: auto;
  width: 100%;

  &__table {
    font-family: Rob;
    font-size: 16px;
    color: #fff;
    border-collapse: collapse;

    tr,
    th,
    td {
      border: 1px solid #dddddd;
      text-align: left;
      padding: 8px;
    }
  }
}
</style>
