<template>
  <div class="adminPanel container">
    <router-link :to="{ name: 'Category' }">
      <button type="button" class="btn btn-primary btn-lg">
        Admin Category
      </button>
    </router-link>
    <br> 
    <router-link :to="{ name: 'AdminProduct' }">
      <button type="button" class="btn btn-primary btn-lg">
        Admin Products
      </button>
    </router-link>
    <!-- <router-link :to="{name : 'Gallery'}">
          <button type="button" class="btn btn-primary btn-lg">Admin Gallery</button>
        </router-link> -->
  </div>
</template>
<script>
export default {
  name: "Admin-vue",
};
</script>
<style scoped>
.btn {
  margin-bottom: 20px;
}
</style>
