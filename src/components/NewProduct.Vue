<template>
    <div class="row">
      <div class="card offset-2 col-md-3">
        <div class="card-body tex-center d-flex align-items-center flex-column">
          <img height="128" class="img-responsive text-center mb-3"
               :src="product.selectedImage == null ? '/src/assets/default.png' : product.selectedImage">
          <input ref="file" type="file" style="display: none;" @change="onChange($event)" class="form-control">
          <button class="btn btn-outline-secondary " type="button" @click="$refs.file.click()">Choose Image</button>
        </div>
      </div>
      <div class="col-md-5">
        <div class="col-md-11 card">
          <div class="card-body">
            <div class="form-group">
              <label>Product Name</label>
              <input type="text" class="form-control" placeholder="name">
            </div>
            <div class="row">
              <div class="form-group col-md-6">
                <label>Product Count</label>
                <input type="text" class="form-control" placeholder="count">
              </div>
              <div class="form-group col-md-6">
                <label>Product Cost</label>
                <input type="text" class="form-control" placeholder="cost">
              </div>
            </div>
            <button class="btn btn-outline-info btn-block">Add!</button>
          </div>
        </div>
      </div>
    </div>
</template>


<script>
export default {
    data(){
        return {
            product: {}
        }
    }
}
</script>


<style>

</style>