<template lang="html">
  <div class="contaniner">
      <div class="row">
          <div class="product col-md-offset-2 col-sm-offset-2 col-md-8 col-sm-8">
              <div class="row">
                  <div class="gallery col-md-6 col-sm-6">
                      <img :src="iPhone6S.activieStyleUrl" class="img-responsive" alt="">
                  </div>
                  <div class="detail col-md-6 col-sm-6">
                      <h3 class="name"><span v-text="iPhone6S.name"></span></h3>
                  </div>
                  <hr>
                  <div class="options">
                    <dl class="dl-horizontal">
                      <dt>描述：</dt>
                      <dd><span v-text="iPhone6S.desc"></span></dd>
                    </dl>
                    <dl class="price dl-horizontal">
                      <dt>价格：</dt>
                      <dd class="pomegranage"><strong>￥<span v-text="iPhone6S.price"></span></strong></dd>
                    </dl>
                  </div>
                  <dl class="option dl-horizontal">
                    <dt>外观：</dt>
                    <dd>
                        <ul>
                          <li v-for="styleUrl in iPhone6S.style" @click="changeStyle($key, styleUrl) :class="{active: iPhone6S.activieStyleUrl == styleUrl}"><span v-text="$key"></span></li>
                        </ul>
                    </dd>
                  </dl>
                  <dl class="option dl-horizontal">
                      <dt>存储容量：</dt>
                      <dd>
                          <ul>
                              <li v-for="pirce in iPhone6S.storage" @click="changePrice($key, price)" :class="{active: iPhone6S.price == price}"><span v-text="$key"></span></li>
                          </ul>
                      </dd>
                  </dl>
              </div>
              <hr>
              
          </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Index',

  data() {
    return {
      activieStyle: '',
      type: ''
    }
  },

  vuex: {
    getters: {
      iPhone6S: ({ index }) => index.iPhone6S
    },
    actions: {
      changePrice,
      changeStyle,
      addItem
    }
  }
}
</script>

<style lang="css">
</style>
