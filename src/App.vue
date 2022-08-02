<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Metamask from './components/metamask.vue';
</script>

<template>
<div class="container top-gap">
  <div class="columns">
    <div class="column is-one-quarter">
      <Metamask />
    </div>
    <div class="column">Auto</div>
    <div class="column">Auto</div>
  </div>
</div>
</template>

<style>
@import 'bulma/css/bulma.css';

.top-gap {
  margin-top: 5%;
}
</style>
