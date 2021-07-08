#### 参数说明
|  属性名 | 说明  | 类型  | 默认值  | 可选值  |
| ------------ | ------------ | ------------ | ------------ | ------------ |
|  force   | 是否为强制更新                | Boolean  | true  | true/false  |
|  tabbar | 是否遮盖原生tabbar组件  | Boolean  | true  |  true/false |
- 注:强制更新模式，点击取消更新按钮，会强制关闭APP

------------



#### 在要检查更新的页面，比如登录页，或者首页


     <!-- 更新组件 force 是否强制更新    tabbar：页面是否有原生tabbar组件-->
            <app-update ref="app_update" :force="true" :tabbar="false"></app-update>
            <script>
                import appUpdate from "@/components/yzhua006-update/app-update.vue"
            export default {
                components:{
                    appUpdate
                },
                mounted() {
                    this.$refs.app_update.update();  //调用子组件 检查更新
                },
            }
            </script>
#### update.vue 接口部分代码
    //向后台发起请求，获取最新版本号
        uni.request({
            url: 'http://api.ihuazi.cn/api/data', //仅为示例，并非真实接口地址。
            method: 'POST',
            success: (res) => {
                // 这里的返回的数据跟后台约定
                let data = [{
                    os: 'android',
                    version: '1.0.1', //最新版本
                    note: '我是安卓升级说明',
                    download_url: 'https://dldir1.qq.com/weixin/android/weixin802android1860_arm64.apk', //下载地址 (微信测试)
                }, {
                    os: 'ios',
                    version: '1.0.1', //最新版本
                    note: '我是IOS升级说明', //下载地址
                    download_url: 'https://weixin.qq.com/cgi-bin/download302?check=false&uin=&stype=&promote=&fr=&lang=zh_CN&ADTAG=&url=ios', //微信测试
                }];
            }
        });