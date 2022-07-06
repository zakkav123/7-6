<template>
  <div>
    <table border="1">
      <thead>
        <th>编号</th>
        <th>姓名</th>
        <th>年龄</th>
        <th>图片</th>
      </thead>
      <tbody>
        <tr v-for="item in arr" :key="item.id">
          <slot name="id" :row="item">
            <td>{{ item.id }}</td>
          </slot>
          <slot name="td" :row="item">
            <td>{{ item.name }}</td>
            <td>{{ item.age }}</td>
            <td>
              <a :href="item.headImgUrl" v-if="item.type == 0">{{item.headImgUrl}}</a>
              <img :src="item.headImgUrl" alt="" v-else-if="item.type == 1" />
              <p v-else>{{item.headImgUrl}}</p>
            </td>
          </slot>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    arr: Array,
  },
};
</script>

<style>
</style>