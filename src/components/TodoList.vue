<template>
    <div>
        <el-row :gutter="20">
            <el-col :span="10">
                <el-input type="text" v-model="message"></el-input>
            </el-col>
            <el-col :span="1">
                <el-button type="primary" @click="submit">提交</el-button>
            </el-col>
        </el-row>
        <el-row>
            <el-col :span="11">
                <el-card>
                    <div @click="del(index)" v-for="(item, index) in todoList" :key="item">{{ item }}</div>
                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<script>
export default {
    data() {
        return {
            message: '',
            todoList: [
                '吃饭',
                '喝水',
                '睡觉',
            ]
        }
    },
    methods: {
        submit() {
            this.todoList.push(this.message);
            this.message = '';
        },
        del(index) {
            this.todoList.splice(index, 1);
        },
    }
}
</script>

<style>
input {
    border: 1px solid black;
}
</style>