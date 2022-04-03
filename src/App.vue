<script setup lang="ts">
import { RouterView } from "vue-router";
import CardValue from './components/CardValue.vue'

</script>

<template>
  <header class="header">

    <section class="resume-info">
      <CardValue :description="'Saldo total'" :value="123" :type="'money'" :icon="'sack-dollar-solid'" />
      <CardValue :description="'Investimento'" :value="23" :type="'money'" :icon="'scale-balanced-solid'" />
      <CardValue :description="'Dinheiro lazer'" :value="123" :type="'money'" :icon="'champagne-glasses-solid'" />
    </section>
    
    <section class="actions"></section>


  </header>

  <RouterView />
</template>

<style lang="scss">
@import "./assets/base.css";
</style>
