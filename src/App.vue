<template>
  <div id="app">
    <div id="app" class="container-fluid">
            <div class="content">
                <h1 class="title">Stock de Tiendas</h1>
                <div v-for="(tienda, i) in tiendas" :key="i">
                  <StoreHeroComponent  :name="tienda.name" :address="tienda.address"/>
                  <div class="btn-group mt-4" data-toggle="buttons">
                    <label class="btn btn-warning">
                        <input type="checkbox" checked v-model="tienda.defaultStyles" /> Apply Default Styles
                    </label>
                  </div>
                  <TableComponent :titles="tienda.stock.titles" :entries="tienda.stock.entries"
                    :class="[!tienda.defaultStyles ? tienda.stylesObject: '']" />
                  <br />
                </div>
            </div>
            <div id="bg">
                <img :src="backgroundImg" alt="">
            </div>
        </div>
  </div>
</template>

<script>
import StoreHeroComponent from './components/StoreHeroComponent.vue'
import TableComponent from './components/TableComponent.vue'

export default {
  name: 'App',
  components: {
    StoreHeroComponent,
    TableComponent
},
  data: () => ({
    backgroundImg: './assets/background.jpg',
        tiendas: [
            {
                name: "Tienda 1",
                address: "San Martin 2299",
                stock: {
                    titles: ["ID", "Producto", "Cantidad", "PreView"],
                    entries: [
                        {
                            id: 1,
                            name: "Notebook HP",
                            cantidad: 20,
                            imag: "https://ar-media.hptiendaenlinea.com/catalog/product/cache/b3b166914d87ce343d4dc5ec5117b502/8/V/8VW01LA-1_T1615590539.png"
                        },
                        {
                            id: 2,
                            name: "Notebook Lenovo",
                            cantidad: 40,
                            imag: "https://cdn.shopify.com/s/files/1/0511/7499/8190/products/Notebook-Lenovo-V15-Amd-Ryzen-5-15-Win10-pos-1@2x.jpg?v=1646335165"
                        },
                        {
                            id: 3,
                            name: "Tablet Samsung",
                            cantidad: 15,
                            imag: "https://images.samsung.com/is/image/samsung/ar-galaxy-taba-t290-sm-t290nzkaaro-frontblack-172109528?$2160_1728_PNG$"
                        },
                        {
                            id: 4,
                            name: "Teléfono Samsung",
                            cantidad: 25,
                            imag: "https://images.samsung.com/is/image/samsung/assets/latin/2203/galaxy-a-series/04_Product_list_A53_5g_mo.png?$FB_TYPE_J_F_MO_PNG$"
                        }
                    ],
                },
                stylesObject: { 'crimson-font': true, 'light-mode': true },
                defaultStyles: false
            },
            {
                name: "Tienda 2",
                address: "San Martin 2299",
                stock: {
                    titles: ["ID", "Producto", "Cantidad", "PreView"],
                    entries: [
                        {
                            id: 5,
                            name: "Notebook Mac",
                            cantidad: 20,
                            imag: "https://ar-media.hptiendaenlinea.com/catalog/product/cache/b3b166914d87ce343d4dc5ec5117b502/8/V/8VW01LA-1_T1615590539.png"
                        },
                        {
                            id: 6,
                            name: "Notebook MacBook",
                            cantidad: 40,
                            imag: "https://media.gq.com.mx/photos/5f21719a737a9d2e88e6dc7a/2:3/w_1332,h_1998,c_limit/MAC.jpg"
                        },
                        {
                            id: 7,
                            name: "Teléfono Iphone11",
                            cantidad: 15,
                            imag: "https://www.macstation.com.ar/img/productos/small/1680-1111.jpg"
                        },
                        {
                            id: 8,
                            name: "Teléfono Iphone13",
                            cantidad: 25,
                            imag: "https://www.apple.com/newsroom/images/product/iphone/geo/Apple_HowToBuy_iPhone-13_GEO_09162021_carousel.jpg.large.jpg"
                        },
                    ]
                },
                stylesObject: { 'sienna-font': true, 'burly-mode': true },
                defaultStyles: false
            },
            {
                name: "Tienda 3",
                address: "San Martin 2299",
                stock: {
                    titles: ["ID", "Producto", "Cantidad", "PreView"],
                    entries: [
                        {
                            id: 2,
                            name: "Notebook Lenovo",
                            cantidad: 40,
                            imag: "https://cdn.shopify.com/s/files/1/0511/7499/8190/products/Notebook-Lenovo-V15-Amd-Ryzen-5-15-Win10-pos-1@2x.jpg?v=1646335165"
                        },
                        {
                            id: 5,
                            name: "Notebook Mac",
                            cantidad: 20,
                            imag: "https://ar-media.hptiendaenlinea.com/catalog/product/cache/b3b166914d87ce343d4dc5ec5117b502/8/V/8VW01LA-1_T1615590539.png"
                        },
                        {
                            id: 6,
                            name: "Notebook MacBook",
                            cantidad: 40,
                            imag: "https://media.gq.com.mx/photos/5f21719a737a9d2e88e6dc7a/2:3/w_1332,h_1998,c_limit/MAC.jpg"
                        },
                        {
                            id: 3,
                            name: "Tablet Samsung",
                            cantidad: 15,
                            imag: "https://images.samsung.com/is/image/samsung/ar-galaxy-taba-t290-sm-t290nzkaaro-frontblack-172109528?$2160_1728_PNG$"
                        },
                    ]
                },
                stylesObject: { 'blue-font': true, 'blue-mode': true },
                defaultStyles: false
            }
        ],
  }),
}
</script>

<style scoped>
  @import "../node_modules/bootstrap/dist/css/bootstrap.min.css";
  @import url('https://fonts.googleapis.com/css2?family=Catamaran:wght@900&display=swap');


  *, *:before, *:after {
      box-sizing: border-box;
      font-family: 'Catamaran', sans-serif;
  }

  body {
      font-family: 'Catamaran', sans-serif;
  }

  .content {
      z-index: 2;
      position: relative;
  }

  .title {
      background: -webkit-linear-gradient(45deg, #09009f, #00ff95 80%);
      text-align: center;
      line-height: 100px ;
      margin: 0 auto;
      display: block;
      color: white;
  }

  #bg {
    position: fixed; 
    top: -50%; 
    left: -50%; 
    width: 200%; 
    height: 200%;
  }

  #bg img {
      position: absolute; 
      top: 0; 
      left: 0; 
      right: 0; 
      bottom: 0; 
      margin: auto; 
      min-width: 50%;
      min-height: 50%;
  }
</style>
