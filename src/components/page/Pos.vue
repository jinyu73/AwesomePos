<template>
    <div class="pos">
      <el-row>
          <el-col style="padding:20px" :span="7" class="pos-order" id="order-list">
              <el-tabs>
                  <el-tab-pane label="点餐">
                      <el-table :data="tableData" border style="width:100%">
                          <el-table-column prop="goodsName" label="商品名称"></el-table-column>
                          <el-table-column prop="count" label="数量" width="70"></el-table-column>
                          <el-table-column prop="price" label="金额" width="70"></el-table-column>
                          <el-table-column label="操作" width="100" fixed="right">
                            <template scope="scope">
                                <el-button type="text" size="small">删除</el-button>
                                <el-button type="text" size="small">添加</el-button>
                            </template>
                          </el-table-column>
                      </el-table>
                      <div class="div-btn" align="center">
                         <el-button type="warning">挂单</el-button>
                         <el-button type="danger">删除</el-button>
                         <el-button type="success">结账</el-button>
                      
                      </div>
                  </el-tab-pane>
                  <el-tab-pane label="挂单">挂单</el-tab-pane>
                  <el-tab-pane label="外卖">外卖</el-tab-pane>
              </el-tabs>
          </el-col>
          <el-col style="padding:20px" :span="17">
              <div class="often-goods">
                  <div class="title" align="center">常用商品</div>
                  <div class="often-goods-list">
                    <ul>
                      <li v-for="goods in oftenGoods" :key="goods.goodsId">
                          <span>{{goods.goodsName}}</span>
                          <span class="o-price">￥{{goods.price}}元</span>
                      </li>
                    </ul>
                  </div>
              </div>

              <div class="goods-type">
                <el-tabs>
                  <el-tab-pane label="汉堡">
                    <div>
                      <ul class="cookList">
                        <li>
                          <span class="foodImg"><img /></span>
                          <span class="foodName">香辣鸡腿堡</span>
                          <span class="foodPrice">￥18元</span>
                        </li>
                      </ul>
                    </div>
                  </el-tab-pane>
                  <el-tab-pane label="小食">
                    小食
                  </el-tab-pane>
                  <el-tab-pane label="饮料">
                    饮料
                  </el-tab-pane>
                  <el-tab-pane label="套餐">
                    套餐
                  </el-tab-pane>
                </el-tabs>
              </div>
          </el-col>
      </el-row>
    </div>
</template>

<script>
export default {
  name: 'pos',
  data () {
    return {
      tableData: [{
        goodsName: '香辣鸡腿堡',
        price: 15,
        count: 1
      }, {
        goodsName: '爱心薯条',
        price: 8,
        count: 1
      }, {
        goodsName: '甜筒',
        price: 8,
        count: 1
      }],
      oftenGoods: [{
        goodsId:1,
        goodsName: '香辣鸡腿堡',
        price: 18
      }, {
        goodsId: 2,
        goodsName: '魔法鸡块',
        price: 18
      }, {
        goodsId: 3,
        goodsName: '可乐大杯',
        price: 18
      }, {
        goodsId: 4,
        goodsName: '雪顶咖啡',
        price: 18
      }, {
        goodsId: 5,
        goodsName: '脆皮炸鸡腿',
        price: 18
      }, {
        goodsId: 6,
        goodsName: '香辣鸡翅',
        price: 18
      }, {
        goodsId: 7,
        goodsName: '美味薯条',
        price: 18
      }]
    }
  },
  mounted: function () {
    var orderHeight = document.body.clientHeight
    console.log(orderHeight)
    document.getElementById('order-list').style.height = orderHeight + 'px'
  }
}
</script>

<style scoped lang="stylus">
    .pos-order
        background-color:#f9fafc
        border-right:1px solid #c0ccda
        .div-btn
          margin-top:20px
    .often-goods
        .title
            height:20px
            border-bottom:1px solid #D3dce6
            background-color:#f9fafc
            padding:10px
        .often-goods-list
            li
                list-style:none
                float:left
                border:1px solid #e5e9f2
                padding:10px
                margin:10px
                background-color:#fff
                .o-price
                    color:#58b7ff
    .goods-type
      clear:both
</style>
