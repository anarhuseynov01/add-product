<template>
    <div class="row product-container">
      <app-product v-for="item in productList" :key="item">
          <img class="card-img-top" src="/src/assets/default.png" alt="Card image cap">
            <div class="card-body">
            <h5 class="card-title">Card title</h5>
                <small>
                    <strong>Count : </strong> 1
                </small>
                <br>
                <small>
                    <strong>Cost : </strong> 10
                </small>
                <br>
                <small>
                    <strong>Total : </strong> 10
                </small>
            </div>
      </app-product>
    </div>
</template>


<script>

import Product from './Product'

export default {
    components: {
        appProduct: Product
    },
    data(){
        return {
            productList: [],
        }
    }
}
</script>


<style>

</style>