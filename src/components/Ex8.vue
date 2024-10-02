<template>
    <div class="container center">
        <form @submit.prevent="handleSubmit" class="center pd">
            <h3 class="pd">Thêm mới tài khoản</h3>
            <div class="pd">
                <label for="userName">Họ và tên</label> <br>
                <input type="text" v-model="user.userName">
            </div>
            <div class="pd">
                <label for="email">Email</label> <br>
                <input type="text" v-model="user.email">
            </div>
            <div class="pd">
                <label for="password">Mật khẩu</label> <br>
                <input type="text" v-model="user.password">
            </div>
            <div class="pd">
                <label for="rePassword">Nhập lại mật khẩu</label> <br>
                <input type="text" v-model="user.rePassword">
            </div>
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    const user = ref({
        userName : "",
        email : "",
        password : "",
        rePassword : "",
    });
    const handleSubmit = () =>{
        console.log(user.value);
    }
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