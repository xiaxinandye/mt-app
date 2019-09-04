<template>
  <section class="m-istyle">
    <dl @mouseover="over">
      <dt>有格调</dt>
      <dd
        :class="{active:kind==='all'}"
        kind="all"
      >
        全部
      </dd>
      <dd
        :class="{active:kind==='part'}"
        kind="part"
      >
        约会聚餐
      </dd>
      <dd
        :class="{active:kind==='spa'}"
        kind="spa"
      >
        丽人SPA
      </dd>
      <dd
        :class="{active:kind==='movie'}"
        kind="movie"
      >
        电影演出
      </dd>
      <dd
        :class="{active:kind==='travel'}"
        kind="travel"
      >
        品质出行
      </dd>
    </dl>
    <ul class="ibody">
      <li
        v-for="(item, index) in cur"
        :key="index"
      >
        <el-card
          :body-style="{padding: '0px'}"
          shadow="never"
        >
          <img
            :src="item.img"
            class="image"
          >
          <ul class="cbody">
            <li class="title">
              {{ item.title }}
            </li>
            <li class="pos">
              <span>{{ item.pos }}</span>
            </li>
            <li class="price">
              ￥<em>{{ item.price }}</em><span>/起</span>
            </li>
          </ul>
        </el-card>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  components: {

  },
  data() {
    return {
      kind: 'all',
      list: {
        all: [
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          }
        ],
        part: [
          {
            title: '约会聚餐',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          }
        ],
        spa: [
          {
            title: '丽人SPA',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          }
        ],
        movie: [
          {
            title: '电影',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          }
        ],
        travel: [
          {
            title: '旅游出行',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          },
          {
            title: '耀莱成龙国际影城(温泉镇店)',
            pos: '免押金，可停车，儿童票，杜比全景声厅,60侦厅',
            price: Math.ceil(Math.random() * 400),
            img: '//p0.meituan.net/deal/201105/15/5_0515144655.jpg@736w_416h_1e_1c',
            url: '//abc.com'
          }
        ]
      }
    }
  },
  computed: {
    cur() {
      return this.list[this.kind]
    }
  },
  methods: {
    over(e) {
      const dom = e.target
      const tag = dom.tagName.toLowerCase()
      if (tag === 'dd') {
        this.kind = dom.getAttribute('kind')
      }
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/css/index/artistic.scss";
</style>
