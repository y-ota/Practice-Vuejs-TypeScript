<template>
  <div>
    <h1>カウントアップ</h1>
    <div>現在のカウント: {{current}}</div>
    <button class="up-button" @click="increment()">UP</button>
    <button class="down-button" @click="decrement()">DOWN</button>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class CountUp extends Vue {
  @Prop({ default: 0 })  current!: number;
  increment() {
      this.current++;
      this.$emit("current", this.current);
  }
  decrement() {
      if (this.current > 1) {
          this.current--;
      }
  }
}
</script>
<style scoped lang="scss">
  .up-button {
    width: 100px;
    height: 32px;
  }

  .down-button {
    width: 100px;
    height: 32px;
  }

</style>
