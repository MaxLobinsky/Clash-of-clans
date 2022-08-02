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
import Card from "@/components/UI/Card.vue";
export default {
  components: { Card },
  data() {
    return {
      items: [
        {
          id: 1,
          title: "Archer",
          descr: "Shoots arrows",
          img: require("@/assets/img/archer.png"),
          lvl: 4,
        },
        {
          id: 2,
          title: "Wizard",
          descr: "Throws fireballs",
          img: require("@/assets/img/wizard.png"),
          lvl: 5,
        },
      ],
    };
  },
};
</script>