<template>
    <div class="tb_home">
        <!-- 首页搜索部分 -->
        <div class="tb_search">
            <img src="https://img.alicdn.com/tfs/TB1R5fsgyDsXe8jSZR0XXXK6FXa-281-80.jpg">
            <div class="search_click">
                <div class="click_inputP">
                    <el-input class="inputP_input" v-model="input" placeholder="淘宝网！"></el-input>
                    <p class="inputP_p">搜索</p>
                </div>
                <div class="click_p">
                    <p v-for="item in tbSearchLlist" :key="item.id">{{item.p}}</p>
                </div>
            </div>
        </div>
        <!-- 首页内容图片部分 -->
        <div class="tb_content">
            <div class="content_div" v-for="item in tbContentList" :key="item.id" @mouseenter="changeBorderColor" @mouseleave="changeBorderColorN">
                <div class="content_card" :style="isMouseChange ? {borderColor: '#d3d3d3', cursor:'pointer'} : {borderColor: '#d3d3d3'}" @click="enterStore" >
                    <img :src="item.src">
                    <p>{{item.p}}</p>
                    <div class="card_span">
                        <span>¥{{item.span1}}</span>
                        <span>¥{{item.span2}}</span>
                    </div>
                    <div class="card_shop">
                        <i class="el-icon-s-shop"></i>
                        <span>{{item.shop}}</span>
                    </div>
                    <el-divider></el-divider>
                    <p class="card_sale">{{item.sale}}</p>
                </div>
            </div>
            <div class="content_page">
                <el-pagination background layout="prev, pager, next" :total="10"></el-pagination>
            </div>
            <div class="content_other">
                <span>您是不是想找：</span>
                <div class="other_span" v-for="item in tbContentOtherList" :key="item.id">
                    <span class="nextLine_for">{{item.span}}</span>
                    <span>|</span>
                </div>
            </div>
        </div>
        <!-- 首页页脚部分 -->
        <div class="tb_footer">
            <div class="footer_firstLine">
                <span  v-for="item in tbFooterFirstList" :key="item.id">{{item.span}}</span>
                <img src="../../assets/images/zhenggongwang.png" alt="">
                <span>浙公网安备 33010002000075号</span>
            </div>
            <div class="footer_nextLine">
                <div v-for="item in tbFooterNextList" :key="item.id">
                    <span class="nextLine_for">{{item.span}}</span>
                    <span v-if="item.span !== '达摩院'">|</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Home',
        data(){
            return {
                input: '',
                isMouseChange: false,
                tbSearchLlist: [
                    {p: '一淘限时抢'},
                    {p: '项链女'},
                    {p: '休闲裤'},
                    {p: '保温杯'},
                    {p: '洗衣液'},
                    {p: '卫衣'},
                    {p: '女手表'},
                    {p: '男士t恤'},
                    {p: '窗帘'},
                    {p: '帆布鞋'},
                    {p: '女内衣'},
                ],
                tbContentList: [
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },

                    {
                        src: require('../../assets/images/content_card.webp'),
                        p: '新手淘宝开店免费注册如何开网店教程宝贝代上架货源店铺运营推广',
                        span1: '100.00',
                        span2: '100.00',
                        shop: '闲学旗舰店',
                        sale: '月销 283',
                    },
                ],
                tbContentOtherList: [
                    {span: '斜跨女包'},
                    {span: '女裤'},
                    {span: '笔记本'},
                    {span: '笔袋'},
                    {span: 'mac'},
                    {span: '耐克'},
                    {span: '无线耳机'},
                    {span: '男士t恤'},
                    {span: '苹果'},
                    {span: '男拖鞋'},
                ],
                tbFooterFirstList: [
                    {span: '联系客服'},
                    {span: '开放平台'},
                    {span: '法律声明'},
                    {span: '廉正举报'},
                    {span: 'Taobao.com版权所有 2003-现在'},
                    {span: '增值电信业务经营许可证：浙B2-20070195'},
                ],
                tbFooterNextList: [
                    {span: '阿里巴巴集团', },
                    {span: '淘宝网', },
                    {span: '天猫', },
                    {span: '聚划算', },
                    {span: '全球速卖通', },
                    {span: '阿里巴巴国际交易市场', },
                    {span: '1688', },
                    {span: '1688', },
                    {span: '飞猪', },
                    {span: '阿里云计算', },
                    {span: 'AliOS', },
                    {span: '阿里通信', },
                    {span: '高德', },
                    {span: 'UC', },
                    {span: '友盟', },
                    {span: '虾米', },
                    {span: '阿里星球', },
                    {span: '钉钉', },
                    {span: '支付宝', },
                    {span: '达摩院',}, 
                ],
            }
        },
        methods: {
            changeBorderColor(){
                this.isMouseChange = true;
            },
            changeBorderColorN(){
                this.isMouseChange = false;
            },
            enterStore(){
                this.$router.push('../../Store');
            }
        }
    }
</script>

<style lang="scss" scoped>
.tb_home{
    display: flex;
    flex-direction: column;
}
// 首页搜索部分
.tb_search{
    width: 60%;
    margin-left: 15%;
    display: flex;
    flex-direction: row;
    margin-bottom: 100px;
}
.search_click{
    width: 100%;
    display: flex;
    flex-direction: column; 
}
.click_inputP{
    display: flex;
    flex-direction: row;
}
.inputP_input{
    // 修改element-ui的默认样式
    /deep/ .el-input__inner{
        border: 4px solid red;
        border-radius: 0;
    }
}
.inputP_p{
    margin:0 auto;
    width: 150px;
    height: 40px;
    text-align: center;
    background-color: red;
    color: #fff;
    line-height: 40px;
}
.click_p{
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    p{
        color: #d3d3d3;
        font-size: 10px;
    }
    p:hover{ 
        color:red;
    }
}
// 首页内容图片部分
.tb_content{
    width: 64%;
    height: 1300px;
    margin-left: 15%;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-content: flex-start;
    margin-bottom: 50px;
}
.content_card{
    width: 194px;
    height: 344px;
    padding: 20px 22px;
    border: 1px solid #d3d3d3;
    img{
        width: 100%;
    }
    p{
        color: #d3d3d3;
        font-size: 15px;
        text-align: left; 
        // 超过两行的文字，省略号显示
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
    }
    .card_span{
        text-align: left;
        span:nth-child(2){
            margin-left: 15px;
            color: #d3d3d3;
            font-size: 15px;
            // 删除线
            text-decoration:line-through;
        }
    }
    .card_shop{
        text-align: left;
        margin-top: 10px;
        .el-icon-s-shop{
            margin-right: 10px;
            color: red;
        }
        span{
            color: #d3d3d3;
            font-size: 15px;
        }
    }
    /deep/ .el-divider--horizontal{
        margin: 5px 0;
    }
    .card_sale{
        color: #d3d3d3;
        font-size: 15px;
        text-align: right;
    }
}
#mourse_change{
    border: 1px solid red;
}
.content_page{
    width: 100%;
    height: 20px;
    margin-top: 20px;
}
.content_other{
    width: 100%;
    height: 50px;
    line-height: 50px;
    margin-top: 50px;
    background-color: #d3d3d3;
    display: flex;
    flex-direction: row;
    color: black;
    span{
        margin-left: 5px;
    }
    .other_span{
        display: inline;
        margin-right: 10px;
        span:nth-child(1){
            margin-right: 10px;
        }
    }
}
// 首页页脚部分
.tb_footer{
    width: 64%;
    margin-left: 15%;
    height: 100px;
    span{
        color: #d3d3d3;
        font-size: 10px;
        text-align: left;
        margin-right: 20px;
    }
    .footer_firstLine{
        display: flex;
        flex-direction: row;
        span:hover{ 
            color: black;
        }
    }
    .footer_nextLine{
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        span{
            font-size: 15px;
        }
        span:hover{ 
            color: black;
        }
    }
}
</style>