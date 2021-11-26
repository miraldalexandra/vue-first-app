<template>
  <div>
    <div class="column">
      <h3>assets images</h3>
      <div v-for="img in images" :key="img.id" class="row">
        <img :src="require(`@/assets/${img.path}`)" width="100" />
      </div>
    </div>
    <div class="column">
      <h3>web images</h3>
      <div v-for="img in webImages" :key="img.id" class="row">
        <img :src="img.path" alt="" width="300" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        { id: 1, path: "images/1.jpg" },
        { id: 2, path: "images/2.jpg" },
      ],
      webImages: [
        {
          id: 1,
          path: "https://cdn.pixabay.com/photo/2018/06/29/08/15/doodle-3505459_1280.png",
        },
        {
          id: 2,
          path: "https://cdn.pixabay.com/photo/2020/03/30/18/44/ice-cream-4985161_1280.png",
        },
      ],
    };
  },
};
</script>

<style>
.row {
  display: flex;
  justify-content: center;
  align-items: center;
}
.column {
  display: flex;
  justify-content: center;
  align-items: center;
}
img {
  margin: 1rem;
}
</style>