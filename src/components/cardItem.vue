<template>
  <div class="card  rounded-0 position-relative d-flex">
    <!-- this for span content  new is hidden shape don`t shrank -->

    <p class="mt-3 ml-2 mr-2 d-block " v-if="!newItem"></p>
    <!-- this for span content  new if item is new -->
    <span
      class="new border-bottom border-top text-center mt-2 ml-2 mr-2"
      v-if="newItem"
    >
      <span>
        جديد
      </span>
    </span>
    <!-- image for item  -->
    <div
      :class="
        flexCardVertical
          ? 'd-flex justify-content-around align-items-center'
          : ''
      "
    >
      <div class="image">
        <img
          class="card-img-top bg-transparent w-100"
          :src="imgSrc"
          alt="item new"
        />
      </div>
      <div class="card-body text-center">
        <!-- name item  -->
        <p class="card-title h5">{{ itemName }}</p>
        <!-- price for item -->
        <p class="card-text text-red font-weight-bolder">
          <span>{{ price }}</span
          ><span> ريال</span>
        </p>
        <!-- here is star rating for item -->
        <div class="text-rating" v-if="!oldItem">
          <font-awesome-icon icon="star" />
          <font-awesome-icon icon="star" />
          <font-awesome-icon icon="star" />
          <font-awesome-icon icon="star" />
          <font-awesome-icon icon="star" />
        </div>
        <div
          class="text-danger text-center pt-2 border-top"
          v-else-if="oldItem"
        >
          منتهي الصلاحية
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    "newItem",
    "itemName",
    "price",
    "oldItem",
    "flexCardVertical",
    "imgSrc"
  ],
  data: () => ({})
};
</script>

<style lang="scss"></style>
}
