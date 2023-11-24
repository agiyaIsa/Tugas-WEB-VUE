<template>
    <div>
      <div class="container">
        <div class="row">
          <div class="mr40 mt20">
            <router-link to="/list-Product">
              <img src="../../assets/icons/back.svg">
            </router-link>
          </div>
          <div>
            <h1 class="m0">Add Product</h1>
            <p class="mt5 mb20 tc-green">Make your product looking good for customer</p>
          </div>
        </div>
        <hr class="uline-grey">
        <div class="mt50 row">
  <div class="w20">
    <label class="form-label">Product Image</label>
  </div>
  <div class="w80">
    <input
      class="form-file"
      type="file"
      accept="image/*"
      @change="handleImageUpload"
    >
    <img v-if="productImage" :src="productImage" alt="Product Image">
  </div>
</div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Product Code</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="text"
              placeholder="Product code"
              v-model="productCode"
              :maxlength="8"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Product Name</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="text"
              placeholder="Product name"
              v-model="productName"
              :minlength="5"
              :maxlength="20"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Price</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="number"
              placeholder="Price"
              v-model="price"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Product Description</label>
          </div>
          <div class="w80">
            <textarea
              class="form-textarea"
              placeholder="Masukkan Product Description"
              v-model="productDescription"
            ></textarea>
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Unit</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="text"
              placeholder="Unit"
              v-model="unit"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Min Purchase</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="number"
              placeholder="Masukkan Min purchase"
              v-model="minPurchase"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Max Purchase</label>
          </div>
          <div class="w80">
            <input
              class="form-text"
              type="number"
              placeholder="Masukkan Max purchase"
              v-model="maxPurchase"
            >
          </div>
        </div>
        <div class="mt30 row">
          <div class="w20">
            <label class="form-label">Category</label>
          </div>
          <div class="w80">
            <select class="form-select" v-model="category">
              <option disabled selected>--- Select Category ---</option>
              <option value="1">Category 1</option>
              <option value="2">Category 2</option>
              <option value="3">Category 3</option>
            </select>
          </div>
        </div>
        <div class="flex mt30">
          <router-link to="/list-user">
            <button class="bt-submit-green">Add Product</button>
          </router-link>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'add-product',
    data() {
      return {
        productImage: '',
       productCode: '',
        productName: '',
        price: '',
        productDescription: '',
        unit: '',
        minPurchase: '',
        maxPurchase: '',
        category: ''
      };
    }
  };
  </script>