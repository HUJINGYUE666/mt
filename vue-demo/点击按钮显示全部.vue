<template>
  <div>
    <div v-for="(item, key) in list" v-show="key<num">{{item}}</div>
    <span @click="showMore">{{txt}}</span>
  </div>
</template>
<script src="https://unpkg.com/vue"></script>
<script>
export default {
  props: {},
  data() {
    return {
      list: ["111", "222", "333", "444", "555", "666"],
      isShow: true,
      txt: "显示全部",
      num: 2
    };
  },
  methods: {
    showMore() {
      this.isShow = !this.isShow;
      this.num = this.isShow ? 2 : this.list.length;
      this.txt = this.isShow ? "显示全部" : "收起";
    }
  }
};
</script>

<style  lang="scss">
* {
  padding: 0;
  margin: 0;
}
</style>