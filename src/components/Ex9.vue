<template>
  <div class="container center">
    <form @submit.prevent="handleSubmit" class="pd center">
      <h3 class="pd">Đăng ký tài khoản</h3>
      <div class="pd">
        <label for="userName">Tên sinh viên</label> <br />
        <input type="text" v-model="user.userName" ref="nameInput" />
        <span v-if="errors.userName" class="error">{{ errors.userName }}</span>
      </div>
      <div class="pd">
        <label for="email">Email</label> <br />
        <input type="text" v-model="user.email" />
        <span v-if="errors.email" class="error">{{ errors.email }}</span>
      </div>
      <div class="pd">
        <label for="password">Mật khẩu</label> <br />
        <input type="password" v-model="user.password" />
        <span v-if="errors.password" class="error">{{ errors.password }}</span>
      </div>
      <div class="pd">
        <label for="phone">Số điện thoại</label> <br />
        <input type="text" v-model="user.phone" />
      </div>
      <input type="submit" value="Submit" class="btn" />
      <p v-if="successMessage" class="success">{{ successMessage }}</p>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const user = ref({
  userName: "",
  email: "",
  password: "",
  phone: "",
});
const errors = ref({});
const successMessage = ref("");
const nameInput = ref(null);

const emailExists = (email) => {
  const storedUsers = JSON.parse(localStorage.getItem("users")) || [];
  return storedUsers.some((storedUser) => storedUser.email === email);
};

const validateForm = () => {
  errors.value = {};

  if (!user.value.userName) {
    errors.value.userName = "Tên sinh viên không được để trống.";
  }
  if (!user.value.email) {
    errors.value.email = "Email không được để trống.";
  } else if (emailExists(user.value.email)) {
    errors.value.email = "Email đã tồn tại.";
  }
  if (!user.value.password) {
    errors.value.password = "Mật khẩu không được để trống.";
  }

  return Object.keys(errors.value).length === 0;
};

const handleSubmit = () => {
  if (validateForm()) {
    const storedUsers = JSON.parse(localStorage.getItem("users")) || [];
    storedUsers.push({ ...user.value });
    localStorage.setItem("users", JSON.stringify(storedUsers));

    user.value = {
      userName: "",
      email: "",
      password: "",
      phone: "",
    };

    successMessage.value = "Đăng ký tài khoản thành công";
    nameInput.value.focus();
  }
};
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.container {
  width: 220px;
  height: auto;
  border: 1px solid gray;
  box-sizing: border-box;
}
.pd {
  padding: 8px;
}
.mg {
  margin: 8px;
}
.btn {
  width: 170px;
  padding: 4px;
  background-color: aqua;
  border: 0px;
  border-radius: 4px;
}
.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.error {
  color: red;
  font-size: 12px;
}
.success {
  color: green;
  font-size: 14px;
  margin-top: 10px;
}
</style>
