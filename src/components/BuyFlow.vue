<template>
    <div class="buyflow-container">
        <div class="icon-container">
            <div class="box" @click="$router.push('/products')">
                <box-icon name='shopping-bag'></box-icon>
            </div>
            <div class="box" :class="isCartStep ?'active' :''" @click="$router.push('/cart')">
                <box-icon name='cart'></box-icon>
            </div>
            <div class="box" :class="isCartStep ?'' :'active'" @click="$router.push('/checkout')">
                <box-icon name='credit-card'></box-icon>
            </div>
        </div>
        <div class="word-container">   
            <div class="word"><span>商店</span></div>
            <div class="word"><span>確認購物車</span></div>
            <div class="word"><span>結帳</span></div>
        </div>
    </div>
</template>
<script>
import 'boxicons';

export default {
    name: 'BuyFlow',
    data() {
        return {
        }
    },
    props: [ 'isCartStep' ],
}
</script>
<style lang="less" scoped>
.buyflow-container {
    width: 1200px;
    margin: 50px 0;
    .icon-container {
        position: relative;
        display: flex;
        justify-content: space-between;
        margin-bottom: 10px;
        &::before {
            content: "";
            position: absolute;
            z-index: -1;
            top: 50%;
            width: 100%;
            height: 5px;
            background-color: #f8f2c1;
        }
        .box {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background-color: #f8f2c1;
            cursor: pointer;
        }
        .active {
            background-color: var(--color-dark-yellow);
        }
    }
    .word-container {
        display: flex;
        justify-content: space-between;
        .word {
            width: 80px;
            text-align: center;
        }
    }

}
</style>