<template>
    <div class="wrapper">
        <v-header></v-header>
        <v-left></v-left>
        <div class="content">
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
    import vHeader from './Header.vue';
    import vLeft from './Left.vue';
    export default {
        components:{
            vHeader,
            vLeft,
        },
        methods: {
            getCommon() {
                //查询省市区列表
                this.$axios.post('/express/public/findRegionDataDTOList').then((res)=>{
                    //sessionStorage.setItem('merchantId',1222)
                    window.list.province=res.data.value
                })

            }
        },
        created(){
            /*let token=getUrlParms("token") || this.$route.query.token
            console.log(token);
            if(token){
                sessionStorage.setItem("token",token)
            }*/
            //this.getCommon()
        }
    }
</script>
