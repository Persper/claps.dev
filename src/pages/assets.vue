<template>
  <v-container>
    <c-back-title>Assets</c-back-title>
    <div class="headline">≈0.00783823 BTC</div>
    <div class="subtitle-1">≈$53.30</div>
    <n-link
      is="v-btn"
      v-if="connected"
      to="withdraw"
      class="mt-5"
      block
      color="primary"
      rounded
    >
      Withdraw to Fox.ONE
    </n-link>
    <template v-else>
      <div class="my-4 pa-3 body-2" :class="$style.tips">
        Because we store assets in Mixin Network, you must connect to Mixin or
        Fox.ONE App to withdraw your assets.
        <div class="font-weight-bold text-right">
          Learn more
          <v-icon color="#b67800" small>{{ doubleRight }}</v-icon>
        </div>
      </div>
      <v-btn class="mb-4" block color="primary" rounded>
        Connect with Mixin
      </v-btn>
      <v-btn block color="primary" rounded>
        Connect with Fox.ONE
      </v-btn>
    </template>
    <v-list class="mt-2 mx--4 transparent">
      <v-list-item v-for="item of 3" :key="item">
        <v-list-item-avatar size="42" color="grey" class="mr-3 rounded">
          <v-img />
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="subtitle-2 mb-0">
            BTC
            <span class="float-right">0.00783</span>
          </v-list-item-title>
          <v-list-item-subtitle class="caption">
            Bitcoin
            <span class="float-right">$5147.85</span>
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-container>
</template>
<script lang="ts">
import { mdiChevronDoubleRight } from '@mdi/js'
import { createComponent } from '@vue/composition-api'

export default createComponent({
  setup() {
    return {
      doubleRight: mdiChevronDoubleRight,
      connected: Math.random() > 0.5,
    }
  },
})
</script>
<style lang="scss" module>
.tips {
  background-color: #fff6e6;
  border: 1px solid #ffc24a;
  color: #b67800;
}
</style>