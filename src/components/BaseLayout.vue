<template>
    <div>
      <BaseHeader />
      <slot></slot>
      <BaseFooter />
    </div>
  </template>

<script>

import BaseHeader from './BaseHeader.vue';
import BaseFooter from './BaseFooter.vue';

export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseFooter
}
}
</script>
