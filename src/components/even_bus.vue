<template>
  <div>
    <button
      :style="{ background: red }"
      @click="
        {
          com = 'emil';
          red = 'red';
        }
      "
    >
      邮箱
    </button>
    <button
      :style="{ background: green }"
      @click="
        {
          com = 'phone';
          red = 'green';
        }
      "
    >
      手机
    </button>
    <keep-alive>
      <component :is="com">
        <template v-slot:phone>
          <h1>666</h1>
        </template>
        <template v-slot:emil>
          <h1>777</h1>
        </template>
      </component>
    </keep-alive>
  </div>
</template>

<script>
import emil from "./Emil_one.vue";
import phone from "./phone_one.vue";
export default {
  data() {
    return {
      com: "emil",
      red: "red",
      green: "green",
    };
  },
  components: {
    emil,
    phone,
  },
};
</script>

<style>
button {
  width: 100px;
  height: 60px;
  background-color: hotpink;
}
</style>