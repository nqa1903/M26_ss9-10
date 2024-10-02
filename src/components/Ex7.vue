<template>
  <div class="container center">
    <form @submit.prevent="handleClick" class="pd center">
      <h3 class="pd">Thêm mới sản phẩm</h3>
      <div class="pd">
        <label for="productCode">Mã sản phẩm</label> <br />
        <input type="text" v-model="product.productCode" />
      </div>
      <div class="pd">
        <label for="productName">Tên sản phẩm</label> <br />
        <input type="text" v-model="product.productName" />
      </div>
      <div class="pd">
        <label for="price">Giá</label> <br />
        <input type="text" v-model="product.price" />
      </div>
      <div class="pd">
        <label for="quantity">Số lượng</label> <br />
        <input type="number" v-model="product.quantity" />
      </div>
      <input type="submit" value="Submit" class="btn"/>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const product = ref({
  productCode: "",
  productName: "",
  price: "",
  quantity: null,
});

const handleClick = () => {
  console.log(product.value);
};
</script>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .container {
        width: 220px ; 
        height: auto;
        border : 1px solid gray;
        box-sizing: border-box;
    }
    .pd{
        padding: 8px;
    }
    .mg{
        margin: 8px;
    }
    .btn{
        width: 170px;
        padding : 4px;
        background-color: aqua;
        border: 0px;
        border-radius: 4px;
    }
    .center{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>
