<template>
    <div class="login">
        <el-row>
            <el-col>
                <div class="header">
                    <img src="" alt="">
                </div>
            </el-col>
        </el-row>
        <el-row>
            <el-col>
                <el-form :model="form" label-width="120px" :rules="loginRuls" ref="formRef">
                    <el-form-item label="" prop="userName">
                        <el-input v-model="form.userName" :prefix-icon="Avatar" />
                    </el-form-item>
                    <el-form-item label="" prop="userPass">
                        <el-input v-model="form.userPass" type="password" :prefix-icon="Key" />
                    </el-form-item>
                    <el-form-item>
                        <el-button class="login-btn" type="primary" @click="onSubmit">登录</el-button>
                    </el-form-item>
                </el-form>
            </el-col>
        </el-row>

    </div>
</template>
<script lang="ts" setup>
import { reactive, ref } from 'vue'
import type { FormInstance, FormRules } from 'element-plus'
import { Avatar, Key } from '@element-plus/icons-vue'

//登陆输入框信息展示
const form = reactive({
    userName: 'admin',
    userPass: '111111',
})

//登录按钮事件
const onSubmit = () => {
    console.log(form)
}

//登录表单校验
const loginRuls = reactive<FormRules>({
    userName: [{ required: true, message: '请输入用户名' }],
    userPass: [{ required: true, message: '请输入密码' }]
})

const formRef = ref<FormInstance>()

</script>
<style setup>
.login {
    width: 400px;
}

.login-btn {
    width: 400px;
}
</style>
