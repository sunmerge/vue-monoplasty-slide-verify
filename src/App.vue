<template>
  <div id="app">
        <div class="border">
            本地图片：
            <slide-verify @success="onSuccess" @fail="onFail1" @refresh="onRefresh" :slider-text="text" :image="curImg"></slide-verify>
            <button @click="onRefresh">刷新</button>
        </div>

        <div class="border">
            网络图片：
            <slide-verify @success="onSuccess" @fail="onFail2" @refresh="onRefresh2" :slider-text="text"></slide-verify>
        </div>

        <div>{{msg}}</div>
  </div>
</template>

<script>
import image1 from "./assets/img/image1.png";
import image2 from "./assets/img/image2.png";
import image3 from "./assets/img/image3.png";
    export default {
        name: 'App',
        data(){
            return {
                msg: '',
                text: '滑动解锁',
                curImg:image1
            }
        },
        methods: {
            onSuccess(){
                this.msg = 'login success'
            },
            onFail1(){
                this.msg = 'onFail1'
            },
            onFail2(){
                this.msg = 'onFail2'
            },
            onRefresh(image){
                this.msg = 'onRefresh';
                let val = Math.floor(Math.random() * 3);
                if(val == 2 ) {
                    this.curImg = image1;
                } else if(val == 1 ){
                    this.curImg = image2;
                } else {
                    this.curImg = image3;
                }
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
        margin-top: 60px;
    }
    .border {
        width:330px;
        border:1px solid #555;
        padding:10px;
        margin:10px;
    }
</style>
