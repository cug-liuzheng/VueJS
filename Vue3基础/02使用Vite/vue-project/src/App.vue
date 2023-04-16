<template>
    <h1>{{ msg }}</h1>
    <button @click="changeMsg">点我一下</button>
</template>

<script>
export default {
    data(){
        return {
            msg:"这是一个自定义的网址！"
        }
    },

    /*
        methods 用来指定实例对象中的方法
            - 它是一个对象，可以在它里面定义多个方法
            - 这些方法最终会被挂载到组件实例上
            - 可以直接通过组件实例来调用这些方法
            - methods 中函数的this会被自动绑定为组件实例
    */
    methods:{

        test(){
            console.log(this)   //组件实例， vm
            alert('实例对象的方法')
        },
        changeMsg(){
            this.msg = "新的消息！"
        }
    }

}
</script>

<style>

</style>