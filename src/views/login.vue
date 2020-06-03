<template>
    <div class="test">
        <!-- <h1>this is my name: {{userName}}</h1> -->
        <!-- <button @click="add">addCount</button> -->
    </div>
</template>

<script>

// vue 3.0 初始化状态需要setup方法，定义状态需要调用ref方法
import {
    onBeforeMount,
    onMounted,
    onBeforeUpdate,
    onUpdated,
    onBeforeUnmount,
    onUnmounted,
    onErrorCaptured,
    onRenderTracked,
    onRenderTriggered,
} from "vue";

export default {
    setup() {
        console.log("this is setup entry");
        onRenderTracked(() => {
        console.log("onRenderTracked");
        });
        onRenderTriggered(() => {
        console.log('onRenderTriggered')
        });
        onBeforeMount(() => {
        console.log("onBeforeMount");
        });
        onMounted(() => {
        console.log("onMounted");
        });
        onBeforeUpdate(() => {
        console.log("onBeforeUpdate");
        });
        onUpdated(() => {
        console.log("onUpdated");
        });
        onBeforeUnmount(() => {
        console.log("beforeDestroy");
        });
        onUnmounted(() => {
        console.log("onUnmounted");
        });
        onErrorCaptured(() => {
        console.log("onErrorCaptured");
        });
        return {
            // count: ref(0)
        }
    },
    created() {
        console.log("this is init")
    },
}
</script>

<style lang="scss" scoped>
.test {
  color: red;
}
</style>