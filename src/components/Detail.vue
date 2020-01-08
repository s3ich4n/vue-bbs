<template>
  <div>
    <tr>
      <td>{{ data.writer }}</td>
      <td>{{ data.title }}</td>
      <td>{{ data.content }}</td>
      <button v-on:click="updateData">수정</button>
      <button v-on:click="deleteData">삭제</button>
    </tr>
  </div>
</template>

<script>
import data from "@/data";

export default {
  name: "Detail",
  data() {
    const index = this.$route.params.contentId;
    return {
      data: data[index],
      index: index
    };
  },
  methods: {
    deleteData() {
      data.splice(this.index, 1); // 해당 인덱스 단 하나를 삭제
      this.$router.push({
        path: "/"
      });
    },
    updateData() {
      this.$router.push({
        name: "Create",
        params: {
          contentId: this.index // router로 옮겨왔을 때 index값으로 가져온 놈을 여기 넣는모양임
        }
      });
    }
  }
};
</script>

<style>
</style>