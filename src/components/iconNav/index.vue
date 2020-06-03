
<template>
    <footer id="icon_nav">
        <div v-for="(item,index) in iconConfig" :key="index" class="icon-item">
            <i>{{item.icone}}</i>
            <div>{{item.name}}</div>
        </div>
    </footer>
</template>

<script>
    /**
     * 说明：功能icon区
     * @param iconConfig {model} 底部导航配置参数
     * @emit iconChange {function} 当前点击得导航模块
     */
    export default {
        props: {
            iconConfig: {
                type: Array,
                default: () => []
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