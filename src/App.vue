<template>
    <div id="app">
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link> |
            <router-link to="/login">Test</router-link>
        </div>
        <router-view/>
        <h2>Hello World Vue3.0</h2>
        <h2>this is myName {{userName}}</h2>
        <h2>this is myCity {{city}}</h2>
        <button @click="getCity">你来自哪里？</button>
        <foot-bar :barJsonConfig="barJsonConfig"></foot-bar>
    </div>
</template>

<script>
    /**
     * 1. setup() 函数是 vue3 中统一的入口函数,所有生命周期函数定义都是需要定义在此函数下才生效
     *    sutup 函数无法访问到this,可接受两个参数:props,context.
     * 2. reactive() 函数接收一个普通对象,返回一个响应式的数据对象. 多一层对象
     * 3. ref() 函数用来根据给定的值创建一个响应式的数据对象，ref() 函数调用的返回值是一个对象，这个对象上只包含一个 .value 属性。
     * 4. isRef() 用来判断某个值是否为 ref() 创建出来的对象。 isProxy、isReactive、isReadonly都大同小异
     * 5. toRefs()可以將reactive多层对象类型的响应对象，转化为普通类型的响应数据. 少一层对象
     */
    import footBar from "./components/footerBar/index.vue";
    import {reactive, ref, isRef, toRefs} from "vue";

    export default {
        components: {
            footBar
        },
        setup() {
            const city = ref("")
            const userInfo = reactive({userName: "小花"});
            const getCity = () => {
                city.value = "BeiJin";
                console.log(isRef(city),isRef(userInfo))
            }
            return {
                barJsonConfig: [{
                    icon: "",
                    homeText: "首页"
                },{
                    icon: "",
                    homeText: "分类"
                },{
                    icon: "",
                    homeText: "直播"
                },{
                    icon: "",
                    homeText: "我的"
                }],
                ...toRefs(userInfo),
                city,
                getCity
            }
        }
    }
</script>

<style lang="scss" scoped>

* {
    margin: 0;
    padding: 0;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

#nav {
    padding: 30px;

    a {
        font-weight: bold;
        color: #2c3e50;

        &.router-link-exact-active {
            color: #42b983;
        }
    }
}
</style>
