<template>
  <div class="m-menu">
    <dl class="nav">
      <dt>全部分类</dt>
      <dd
        v-for="(item, index) in menu"
        :key="index"
        @mouseenter="enter"
        @mouseleave="mouseleave"
      >
        <i :class="item.type" />{{ item.name }}<span class="arrow" />
      </dd>
    </dl>

    <div
      v-if="kind"
      class="detail"
      @mouseenter="sover"
      @mouseleave="sout"
    >
      <template v-for="(item, index) in curdetail.child">
        <h4 :key="index">
          {{ item.title }}
        </h4>
        <span
          v-for="v in item.child"
          :key="v"
        >{{ v }}</span>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: '',
      menu: [{
        type: 'food',
        name: '美食',
        child: [{
          title: '美食',
          child: ['代金券', '甜点饮品', '火锅', '自助餐', '小吃快餐']
        }]
      }, {
        type: 'takeout',
        name: '外卖',
        child: [{
          title: '外卖',
          child: ['美团外卖']
        }]
      }, {
        type: 'hotel',
        name: '酒店',
        child: [{
          title: '酒店星级',
          child: ['经济型', '舒适/三星', '高档/四星', '豪华/五星']
        }]
      }, {
        type: 'homestay',
        name: '榛果名宿',
        child: [{
          title: '热门城市',
          child: ['北京', '上海', '广州', '深圳', '成都']
        }, {
          title: '热门房源',
          child: ['复式Loft', '别墅']
        }]
      }, {
        type: 'movie',
        name: '猫眼电影',
        child: [{
          title: '热映电影',
          child: ['速度与激情：特别行动', '铤而走险', '深夜食堂', '徒手攀岩']
        }, {
          title: '热门影院',
          child: ['SFC上影影城', '万达影城', '星美国际影城', '博纳国际影城']
        }]
      }, {
        type: 'airport',
        name: '机票 / 火车票',
        child: [{
          title: '机票',
          child: ['国内机票', '国际/港澳台机票']
        }, {
          title: '火车票',
          child: ['火车票']
        }]
      }, {
        type: 'ktv',
        name: '休闲娱乐 / KTV',
        child: [{
          title: '休闲娱乐',
          child: ['足疗按摩', '私人影院', 'VR', '游乐游艺']
        }]
      }]
    }
  },
  computed: {
    curdetail() {
      // 过滤器，传入参数为menu数组
      return this.menu.filter(item => item.type === this.kind)[0]
    }
  },
  methods: {
    enter(e) {
      this.kind = e.target.querySelector('i').className
      clearTimeout(this._timer)
    },
    mouseleave() {
      this._timer = setTimeout(() => {
        this.kind = ''
      }, 150)
    },
    sover() {
      clearTimeout(this._timer)
    },
    sout() {
      this.kind = ''
    }
  }
}
</script>

<style>
</style>
