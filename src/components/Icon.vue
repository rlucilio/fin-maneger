<script lang="ts" setup>
import { onMounted } from 'vue';

const props = defineProps({
  name: { type: String, required: true },
  height: { type: Number, default: 40 },
  width: { type: Number, default: 40 },
  withBackground: { type: Boolean, default: true }
})

const size = {
  width: `${props.width}px`,
  height: `${props.height}px`
}

</script>


<template>
  <main class="container" :style="size" :class="{ '-with-background': props.withBackground }">
    <div class="icon" :style="{background: `url(/src/assets/icons/${props.name}.svg)`}" />
  </main>
</template>

<style lang="scss" scoped>

.container {
  .icon {
    width: 100%;
    height: 100%;
  }

  &.-with-background {
    background-color: var(--icon-background);
    border-radius: 100%;
    padding: 10px;
  }
}
.sack-dollar-solid {
  background: url(../assets/icons/sack-dollar-solid.svg);
}

.scale-balanced-solid {
  background: url(../assets/icons/scale-balanced-solid.svg);
}
</style>

