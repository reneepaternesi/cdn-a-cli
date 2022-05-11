<template>
  <div class="store-hero-wrapper">
    <h2 class="store-name">{{name}}</h2> - <h4 class="store-address">{{address}}</h4>
  </div>
</template>

<script>
export default {
     name: 'StoreHeroComponent',
     props: {
        name: {
            type: String,
            required: true
        },
        address: {
            type: String,
            required: true
        },
     }
}
</script>

<style>
  .store-hero-wrapper {
      text-align: center;
      line-height: 100px;
  }

  .store-hero-wrapper .store-name, .store-hero-wrapper .store-address{
      display: inline-block;
      
  }
</style>