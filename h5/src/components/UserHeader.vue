<template>
    <div class="userheader">
        <!--<div class="topcolor"></div>-->
        <div class="userimg">
            <div class="headerimg">
                <input name="file" type="file" accept="image/png,image/gif,image/jpeg,image/jpg" @change="upload($event)"/>
                <img :src="avatar"/>
                <p>{{ name }}</p>
            </div>
            <div class="user-setting">
                <i class="iconfont icon-shezhi" @click="setting"></i>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['avatar', 'name'],
    methods: {
        setting () {
            this.$router.push({path: '/setting'})
        },
        // 头像上传
        upload (e) {
            this.$emit('upload', e)
        }
    }
}
</script>

<style>
    .headerimg input {
        position: absolute;
        top: 40%;
        transform: translateY(-50%);
        width: 1.5rem;
        height: 1.5rem;
        border-radius: 50%;
        opacity: 0;
        z-index: 5;
    }
</style>
