<template>
  <div>
    <input v-model="writer" placeholder='글쓴이'/>
    <input v-model="title" placeholder='제목'/>
    <textarea v-model="content" placeholder="내용"/>
    <button v-on:click="write">작성</button>
  </div>
</template>

<script>
import data from '@/data';

export default {
  name: 'Create',
  data() {
    return {
      data: data,
      writer: "",
      title: "",
      content: ""
    }
  },
  methods: {
    write() {
      console.log("글쓰기 추가중...")
      this.data.push({
        writer: this.writer,
        title: this.title,
        content: this.content,
      })
      this.$router.push({
        path: '/'
      })
    }
  }
}
</script>

<style>

</style>