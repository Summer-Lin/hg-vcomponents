<template>
  <div>
    <h4 class="title">滑动删除组件</h4>
    <ul class="silddelete">
      <li v-for="item in data" v-if="item.show">
        <slid-delete :height="'50px'" :delWidth="60" @deteleClicked="delCelue(item)">
          <div>{{item.content}}</div>
        </slid-delete>
      </li>
    </ul>
  </div>
</template>

<script>
import { SlidDelete } from '@/components';

export default {
  name: 'el-sliddelete',
  data () {
    return {
      data: [{
        show: true,
        content: '飞流直下三千尺'
      }, {
        show: true,
        content: '疑是银河落九天'
      }, {
        show: true,
        content: '欲把西湖比西子'
      }, {
        show: true,
        content: '淡妆浓抹总相宜'
      }]
    };
  },
  components: {
    SlidDelete
  },
  methods: {
    delCelue (item) {
      item.show = false;
    }
  }
};
</script>

<style lang="scss" scoped>
h4.title {
  text-align: center;
  padding: 20px 0;
}
.silddelete {
  line-height: 50px;
  color: #2c3e50;
  text-align: center;
  li {
    div {
      background-color: #F2F2F2;
      border-bottom: 1px solid #b2d2f1;
    }
  }
}
</style>
