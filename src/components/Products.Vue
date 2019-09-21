<template>
    <div v-if="productList.length !== 0">
        <h3 class="text-center">Added Product Lists</h3>
        <hr>
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
            if(this.productList.length < 10){
                this.productList.push(data);
                eventBus.$emit("progressBarUpdate",this.productList.length)
            } else {
                alert('10 dan artiq product elave etmek olmaz!');
            }
    
        })
    }
}
</script>


<style>

</style>