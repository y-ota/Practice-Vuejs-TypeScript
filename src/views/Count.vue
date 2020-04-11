<template>
  <div class="home">
    <CountUp current="4" @current="test"/>
    <img alt="Vue logo" src="../assets/logo.png">
  </div>
</template>

<script lang="ts">
import CountUp  from '@/components/CountUp.vue'
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component({
  components:{CountUp}
})
export default class Count extends Vue {

  private test(value: any): void {
    console.log(value);
  }
}
</script>
