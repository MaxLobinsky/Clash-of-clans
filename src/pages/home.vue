<template>
  <carousel :settings="settings" :breakpoints="breakpoints">
    <slide class="card__wrapper" v-for="item in items" :key="item.id">
      <Card
        :name="`${item.lvl} lvl`"
        :title="item.title"
        :imgURL="item.img"
        :link="`/${item.alias}`"
      >
        <template v-slot:body>
          {{ item.descr }}
        </template>
        <template v-slot:footer>
          <CardFooter :item="item" />
        </template>
      </Card>
    </slide>
    <template #addons>
      <navigation />
    </template>
  </carousel>
</template>

<script>
import items from "@/seeders/items.js";
import Card from "@/components/UI/Card.vue";
import CardFooter from "@/components/UI/CardFooter.vue";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation } from "vue3-carousel";
export default {
  components: {
    CardFooter,
    Card,
    Carousel,
    Slide,
    Navigation,
  },
  data() {
    return {
      items: items,
      settings: {
        itemsToShow: 2,
        wrapAround: true,
        snapAlign: "center",
      },
      breakpoints: {
        300: {
          itemsToShow: 1,
        },
        700: {
          itemsToShow: 2,
        },
      },
    };
  },
};
</script>