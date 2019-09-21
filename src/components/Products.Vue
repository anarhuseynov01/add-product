<template>
    <div class="row product-container">
      <app-product v-for="item in productList" :key="item">
          <img class="card-img-top" :src="item.selectedImage" :alt="item.title">
            <div class="card-body">
            <h5 class="card-title">{{item.title}}</h5>
                <small>
                    <strong>Count : </strong> {{item.count}}
                </small>
                <br>
                <small>
                    <strong>Cost : </strong> {{item.cost}}
                </small>
                <br>
                <small>
                    <strong>Total : </strong> {{item.total}}
                </small>
            </div>
      </app-product>
    </div>
</template>


<script>

import Product from './Product'
import { eventBus } from '../main'

export default {
    components: {
        appProduct: Product
    },
    data(){
        return {
            productList: [],
        }
    },
    created(){
        eventBus.$on("productAdded",(data)=>{
            this.productList.push(data)
        })
    }
}
</script>


<style>

</style>