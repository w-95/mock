
<template>
    <footer id="footer">
        <div v-for="(item,index) in barJsonConfig" :key="index" class="home-item">
            <i>{{item.icone}}</i>
            <div>{{item.homeText}}</div>
        </div>
    </footer>
</template>

<script>
    /**
     * 说明：底部bar导航组件
     * @param isShowFoot {model} 是否显示底部导航栏 默认为true（显示）
     * @param barJsonConfig {model} 底部导航配置参数
     * @emit selectedChange {function} 当前点击得导航模块
     */
    export default {
        props: {
            barJsonConfig: {
                type: Array,
                default: () => []
            },
            isShowFoot: {
                type: Boolean,
                default: true
            }
        },
        setup(props,context) {

        },
    };
</script>

<style lang="scss" scoped>
#footer {
    width: 100%;
    height: 50px;
    display: flex;
    margin: 0 auto;
    background-color: #fff;
    box-shadow: 0 -2px 4px rgba(0, 0, 0, .06);
    position: fixed;
    bottom: 0;
    .home-item {
        flex: 1;
        padding-top: 8px;
        div{
            font-size: 10px;
            text-align: center;
        }
    }
}
</style>