# vue-monoplasty-slide-verify

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```
## Quick Start

###  1. Import vue-monoplasty-slide-verify into your vue.js project.

Using build tools:

```bash
cnpm install --save git+https://gitee.com/migloo/vue-monoplasty-slide-verify.git#v1.0.5

v1.0.5:标签名
```

```js
import Vue from 'vue';
import SlideVerify from 'vue-monoplasty-slide-verify';

Vue.use(SlideVerify);
```

### 2. Now you have it. The simplest usage:

```html
<slide-verify :l="42"
            :r="10"
            :w="310"
            :h="155"
            slider-text="向右滑动"
            @success="onSuccess"
            @fail="onFail"
            @refresh="onRefresh"
            :image="img"
            ></slide-verify>
<div>{{msg}}</div>
```

```js
import image1 from "./assets/img/image1.png";
import image2 from "./assets/img/image2.png";
export default {
        name: 'App',
        data(){
            return {
                msg: '',
                img:image1
            }
        },
        methods: {
            onSuccess(){
                this.msg = 'login success'
            },
            onFail(){
                this.msg = ''
            },
            onRefresh(){
                this.msg = '',
                this.img=image2;
            }
        }
    }
```

## Document

### argument

| Param | Type | Describe |
| :------: | :------: | :------: |
| l | Number | block length |
| r | Number | block circle radius |
| w | Number | canvas width |
| h | Number | canvas height |
| sliderText | String | Slide filled right |
| image | String or null | 自定义控件显示的图片，如果不设置或者设置为null，则从网络随机获取图片|

### callBack

| Event | Type | Describe |
| :------: | :------: | :------: |
| success | Function | success callback |
| fail | Function | fail callback |
| refresh | Function | refresh button callback |


## Log
### V1.0.2
- Mobile terminal touch event support
### V1.0.5
- add slider text
