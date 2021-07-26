<template>
    <div class="store">
        <!-- 店铺名称 -->
        <div class="store_name">
            <img src="//gdp.alicdn.com/imgextra/i2/3070955695/TB29pWms5CYBuNkHFCcXXcHtVXa_!!3070955695.jpg" alt="">
        </div>
        <!-- 店铺内容 -->
        <div class="store_content">
            <div class="content_leftImg">
                <el-carousel>
                    <el-carousel-item v-for="item in contentLeftImgList" :key="item.id">
                        <img :src="item.src" alt="">
                    </el-carousel-item>
                </el-carousel>
            </div>
            <div class="content_rightInfo">
                <el-form ref="contentRightInfoData" :model="contentRightInfoData" label-width="80px">
                    <p>项链女纯银梦幻星球玫瑰金吊坠潮小众轻奢锁骨链简约气质生日礼物</p>
                    <div class="rightInfo_span">
                        <span>免费刻字</span>
                        <span>代写贺卡</span>
                        <span>精美包装</span>
                    </div>
                    <div class="rightInfo_price">
                        <span>价格</span>
                        <span>¥</span>
                        <span>{{contentRightInfoData.price}}</span>
                    </div>
                    <div class="rightInfo_amount">
                        <span>数量</span>
                        <el-input-number v-model="num" :step="1" :min="0" @change="chagneShopAmount"></el-input-number>
                    </div>
                    <div class="rightInfo_totalAmount">
                        <span>合计</span>
                        <el-input size="small" v-model="contentRightInfoData.totalAmount"></el-input>
                        <span>元</span>
                    </div>
                    <div class="rightInfo_shop">
                        <el-button type="danger" plain>立即购买</el-button>
                        <el-button type="danger" icon="el-icon-shopping-cart-2">加入购物车</el-button>
                    </div>
                </el-form>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'store',
        data(){
            return {
                num: 0,
                contentRightInfoData: {
                    price: 200,
                    totalAmount: 0,
                },
                contentLeftImgList: [
                    {src: require("../../assets/images/store_img1.jpg")},
                    {src: require("../../assets/images/store_img2.jpg")},
                    {src: require("../../assets/images/store_img1.jpg")},
                    {src: require("../../assets/images/store_img2.jpg")},
                ]
            }
        },
        methods: {
            chagneShopAmount(num){
                this.contentRightInfoData.totalAmount = this.contentRightInfoData.price * num;
            }
        }
    }
</script>

<style lang="scss" scoped>
.store{
    width: 80%;
    margin-left: 10%;
}
// 店铺内容
.store_content{
    width: 100%;
    margin-left: 15%;
    margin-top:50px;
    display: flex;
    flex-direction: row;
    // 店铺内容左边图片
    .content_leftImg{
        width: 280px;
        height: 310px;
        .el-carousel{
            img{
                height: 100%;
                width: 100%;
            }
        }
    }
    // 店铺内容右边信息
    .content_rightInfo{
        display: flex;
        flex-direction: column;
        margin-left: 100px;
        p{
            font-size: 20px;
            font-weight: bold;
            margin: 0;
        }
        span{
            font-size: 15px;
            margin: 0;
            text-align: left;
        }
        .rightInfo_span{
            font-size: 15px;
            color: red;
            margin: 0;
            text-align: left;
        }
        .rightInfo_price{
            width: 100%;
            height: 50px;
            margin: 10px 0;
            background-color: #e9e9e9;
            display: flex;
            flex-direction: row;
            span:nth-child(1){
                line-height: 50px;
                padding-left: 10px;
                padding-right: 150px;
            }
            span:nth-child(2), span:nth-child(3){
                font-size: 25px;
                color: red;
                font-weight: bold;
                line-height: 50px;
            }
        }
        .rightInfo_amount{
            display: flex;
            flex-direction: row;
            span{
                margin-right: 50px;
            }
        }
        .rightInfo_totalAmount{
            margin: 20px 0;
            display: flex;
            flex-direction: row;
            span:nth-child(1){
                padding-right: 50px;
            }
            .el-input{
                width: 180px;
            }
        }
        .rightInfo_shop{
            display: flex;
            flex-direction: row;
            justify-content: flex-start;
            margin: 20px 80px;
            .el-button{
                width: 200px;
                height: 40px;
            }
        }
    }
}
</style>