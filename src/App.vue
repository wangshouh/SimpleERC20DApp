<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import Metamask from './components/metamask.vue';
import smartcontract from './components/smartcontract.vue';
</script>

<template>
<div class="container top-gap">
  <div class="columns">
    <div class="column is-3">
      <Metamask />
    </div>
    <div class="column is-6">
      <smartcontract />
    </div>
    <div class="column"></div>
  </div>
</div>
</template>

<style>
@import 'bulma/css/bulma.css';

.top-gap {
  margin-top: 5%;
}
</style>
