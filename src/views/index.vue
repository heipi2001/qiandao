<template>
    <div>
        <!-- <el-container>
            <el-header></el-header>
            <el-main>
                <el-breadcrumb separator-class="el-icon-arrow-right">
                    <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
                    <el-breadcrumb-item>活动管理</el-breadcrumb-item>
                    <el-breadcrumb-item>活动列表</el-breadcrumb-item>
                    <el-breadcrumb-item>活动详情</el-breadcrumb-item>
                </el-breadcrumb>
                <router-view></router-view>   
            </el-main>
        </el-container> -->
        <el-container>
        <el-header><HeadTop/></el-header>
        <el-container>
            <el-aside width="200px"><Aside/></el-aside>
            <el-main>
                <el-breadcrumb separator-class="el-icon-arrow-right">
                <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
                <el-breadcrumb-item>活动管理</el-breadcrumb-item>
                <el-breadcrumb-item>活动列表</el-breadcrumb-item>
                <el-breadcrumb-item>活动详情</el-breadcrumb-item>
                </el-breadcrumb>
                <router-view class="infor"/>
            </el-main>
        </el-container>
        </el-container>
    </div>
</template>

<script>
import HeadTop from '../components/headTop'
import Aside from '../components/aside'
export default{
    components: {
        HeadTop,
        Aside
    }
}
</script>

<style>
.el-aside{
    margin-top: 1px;
}
.el-header{
    padding: 0px;
}
.infor{
    margin-top: 5vh;
}
</style>