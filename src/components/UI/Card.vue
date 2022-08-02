<template>
  <div class="card">
    <div v-if="imgURL" class="card-img__wrapper">
      <img class="card-img" :src="imgURL" :alt="title">
    </div>
    <span class="card-name">{{ name }}</span>
    <span class="card-title">{{ title }}</span>
    <div class="card-body">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    imgURL: {
      type: String,
    },
  },
};
</script>