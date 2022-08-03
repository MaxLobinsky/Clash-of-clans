<template>
  <div class="md-body">
    <div class="card__wrapper" v-for="item in items" :key="item.id">
      <Card :name="`${item.lvl} lvl`" :title="item.title" :imgURL="item.img">
        {{ item.descr }}
      </Card>
    </div>
  </div>
</template>

<script>
import items from "@/seeders/items.js"
import Card from "@/components/UI/Card.vue";
export default {
  components: { Card },
  data() {
    return {
      items: items,
    };
  },
};
</script>