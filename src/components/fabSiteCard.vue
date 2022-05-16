<template>
    <div id="app">
        <div class="fab-site-card" @click="gotosth()">
            <div class="site-card-settings" @click="settings()"></div>
            <div class="site-card-img"></div>
            <div class="site-card-text">bilibili.com</div>
            <a href="https://bilibili.com" id="goto"></a>
        </div> 
        <div class="fab-site-setting" :style="setting">
            <div class="fab-site-setting-close"></div>
            <p>名称</p><input class="fab-site-setting-name" />
            <p>网址</p><input class="fab-site-setting-name" />
        </div>
    </div>

</template>

<script>
    export default {
        name: "fabSiteCard",
        data() {
            return {
                issetting: false
            }
        },
        methods: {
            gotosth() {
                if (this.issetting) {
                    return;
                }
                document.getElementById('goto').click();
            },
            settings() {
                this.issetting = true;
                console.log("awawa");
            }
        },
        computed: {
            setting: function(){
                return{
                    display: this.issetting?"block":"none",
                }
            }
        }
    }
</script>

<style scoped>
    .fab-site-card {
        width: 114px;
        height: 114px;
        border-radius: 10px;

        display: flex;
        flex-direction: column;

        transition: all .2s cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .fab-site-card:hover {
        background-color: #555555;
    }

    .site-card-settings {
        width: 0;
        height: 0;
        border-top: 30px solid rgba(0, 0, 0, 0);
        border-left: 30px solid transparent;

        align-self: flex-end;

        transition: all .2s cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .site-card-settings::before {
        content: "···";
        font-size: 20px;
        color: #00000000;
        position: relative;
        left: -15px;
        top: -35px;
    }

    .site-card-adder {
        width: 0;
        height: 0;
        border-top: 30px solid rgba(0, 0, 0, 0);
        border-left: 30px solid transparent;

        align-self: flex-end;

        transition: all .2s cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .site-card-adder::before {
        content: "···";
        font-size: 20px;
        color: #ffffff00;
        position: relative;
        left: -15px;
        top: -35px;
    }

    .fab-site-card:hover .site-card-settings {
        border-top: 30px solid #444444;
    }

    .fab-site-card:hover .site-card-settings::before {
        color: #ffffff;
    }

    .site-card-img {
        width: 50px;
        height: 50px;
        background-color: #444444;
        border-radius: 16px;

        align-self: center;
    }

    .site-card-text {
        width: auto;
        height: auto;
        color: #ffffff;
        padding-top: 5px;
        font-size: 13px;

        align-self: center;
    }
</style>
