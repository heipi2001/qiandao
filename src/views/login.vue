<!--  -->
<template>
    <div class="login">
        <div class="login_topbar">
            <div class="login_topbar_title">大字</div>
            <div class="login_topbar_titleList">
                <div class="list">小字1</div>
                <div class="list">小字2</div>
                <div class="list">小字3</div>
            </div>
        </div>

        <div :class="[ loginView ? 'login_window_show' : 'login_window', 'login_window_class']">
            <div class="login_window_input">
                <div class="is_input">
                    <div>
                        <el-input placeholder="请输入学习通账号" prefix-icon="el-icon-user-solid" v-model="cx_username"></el-input>
                    </div>
                    <div>
                        <el-input placeholder="请输入学习通密码" show-password prefix-icon="el-icon-question" v-model="cx_password"></el-input>
                    </div>
                    <div>
                        <el-input placeholder="Key-ID" v-model="IsKey">
                            <template slot="prepend">密匙</template>
                        </el-input>
                    </div>
                    <div>
                        <el-switch style="display: block" active-color="#13ce66" inactive-color="#ff4949"
                            v-model="Isadmin" active-text="管理员">
                        </el-switch>
                    </div>
                </div>
                <div class="login_window_input_button">
                    <div class="login_window_input_button_login button" @click="login">登录</div>
                    <div class="login_window_input_button_cancel button" @click="cancel">取消</div>
                </div>
            </div>
        </div>
        <div :class="[ loginView ? 'login_text_hidde' : 'login_text']">
            <div style="font-size:9vh" class="media_hidde">还在担心上课签到吗</div>
            <div style="font-size:8vh;margin:3vh" class="media_hidde">自动签到来啦</div>
            <div style="font-size:2vh" class="media_hidde">妈妈再也不用担心签到过期啦</div>
            <div class="media_font">输入学习通账号密码开始</div>
            <div class="login_text_button" @click="login_view">开始</div>
        </div>
    </div>
</template>

<script>
    export default {

        data() {
            return {
                loginView: false,
                cx_username: '',
                cx_password: '',
                IsKey: '',
                Isadmin: false
            }
        },
        methods: {
            login_view: function () {
                this.loginView = true
            },
            cancel: function () {
                this.loginView = false
            },
            login: function () {
                if (this.cx_username === '') {
                    return this.$message('账号不能为空!');
                }
                if (this.cx_password === '') {
                    return this.$message('密码不能为空!')
                }
                if (this.IsKey === '') {
                    return this.$message('请输入密匙!')
                }
                if (this.Isadmin) {
                    // this.$http.post('/login', {
                    //     username: this.cx_username,
                    //     password: this.cx_password
                    // }).then((res) => {
                    //     console.log(res)
                    // })
                    console.log("i is admin")
                } else {console.log("i is user")}
            }
        },
        //生命周期 - 创建完成（访问当前this实例）
        created() {

        },
        //生命周期 - 挂载完成（访问DOM元素）
        mounted() {

        }
    }
</script>

<style>
    /* @import url(); 引入css类 */
    body {
        background-size: 100% auto;
        background-repeat: no-repeat;
        background-image: url("../assets/david-vig-qwHHOC2z5Xs-unsplash.jpg");
    }

    .el-switch__label {
        color: #909399;
    }

    .el-switch__label.is-active {
        color: #303133;
    }

    .button {
        width: 10vh;
        height: 4vh;
        border-radius: 0.5vh;
        line-height: 4vh;
        background: #1bba9b;
    }

    .is_input {
        padding: 3vh;
        height: 40%;
        width: 60%;
        margin: auto;

    }

    .is_input>div>.el-input,
    .el-switch {
        margin: 1vh;
    }

    .login {
        width: 100%;
        height: 100vh;
        position: relative;
        background: rgba(0, 0, 0, 0.3);
        overflow: hidden;
    }

    .login_topbar {
        width: 100%;
        height: 7vh;
        position: absolute;
        top: -8px;
        left: 0px;
        line-height: 7vh;
    }

    .login_topbar_title {
        font-weight: bold;
        font-size: 3vh;
        position: absolute;
        color: #FFFF;
        left: 10vh;
    }

    .login_topbar_titleList {
        color: #FFFF;
        display: flex;
        position: absolute;
        right: 15vh;
    }

    .list {
        width: 10vh;
        font-size: 2vh;
    }

    .login_window_class {
        transition: 1s all ease-in-out;
        margin: 25vh auto;
        width: 30%;
        position: absolute;
        left: 37.5%;
        background: #FFFFFF;
        height: 47vh;
        border-radius: 3vh;
        box-shadow: 0px 0px 70px black;
    }

    .login_window {
        top: -1000px;
    }

    .login_window_show {
        top: 0vh;
    }

    .login_window_input {
        height: 100%;
        width: 80%;
        margin: auto;
        display: flex;
        flex-direction: column;
    }

    .login_window_input_button {
        text-align: center;
        display: flex;
        margin: auto;
        color: #FFFF;
    }

    .login_window_input_button_cancel {
        background: #FFF;
        margin-left: 5vh;
        color: #000000;
    }

    .login_window_text {
        display: block;
        font-size: 2.5em;
        font-weight: bold;
        color: #FFF;
        margin-bottom: 5vh;
    }

    .login_text {
        color: #FFFF;
        width: 60%;
        height: 50vh;
        position: absolute;
        top: 20vh;
        left: 40vh;
        text-align: center;
        transition: 1s all ease-in-out;
    }

    .login_text_hidde {
        transition: 1s all ease-in-out;
        color: #FFFF;
        width: 60%;
        height: 50vh;
        position: absolute;
        left: 40vh;
        top: 2000px;
        text-align: center;
    }

    .login_text_button {
        margin: 10vh auto;
        width: 15vh;
        height: 5vh;
        border-radius: 1vh;
        line-height: 5vh;
        background: #1bba9b;
    }

    .media_font {
        display: none;
    }

    @media screen and (max-width: 1024px) {
        .login_topbar_title {
            display: none;
        }

        body {
            background-size: auto 100%;
            background-repeat: no-repeat;
            background-image: url("../assets/david-vig-qwHHOC2z5Xs-unsplash.jpg");
        }

        .login_text {
            left: 0px;
            font-size: 1.5em;
        }

        .media_font_little {
            display: none;
        }

        .media_hidde {
            display: none;
        }

        .login_text_button {
            margin: 5vh;
        }

        .media_font {
            display: block;
            font-size: 9vh;
        }

        .login_window_class {
            left: 5vh;
            height: 55%;
            width: 80%;
        }
    }

    @media screen and (max-height: 665px) {
        .login_window_class {
            height: 70vh;
        }
    }
</style>