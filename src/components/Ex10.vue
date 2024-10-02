<template>
    <div>
        <form @submit.prevent="handleSubmit">
            <h3>Đăng nhập tài khoản</h3>
            <div>
                <label for="email">Email</label>
                <input type="text">
            </div>
            <div>
                <label for="password">Mật khẩu</label>
                <input type="password">
            </div>
            <input type="submit" value="Submit">
        </form>
    </div>
</template>

<script setup>
    
</script>

<style scoped>

</style>