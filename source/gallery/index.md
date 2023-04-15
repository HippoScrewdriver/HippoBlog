---
title: gallery-施工中，现在还很离谱
date: 2023-03-22 19:48:54
type: gallery
---

<style>
        * {
            margin: 0;
            padding: 0;
        }
        .item {
            float: left;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            font-weight: 700;
            color: aliceblue;
            margin-right: 15px;
            margin-bottom: 15px;
            width: 205px;
            position: absolute;
        }
        .item-1 {
            background-color: rgb(206, 169, 169);
            height: 300px;
        }.item-2 {
            background-color: rgb(131, 226, 174);
            height: 150px;
        }.item-3 {
            background-color: rgb(77, 30, 30);
            height: 350px;
        }.item-4 {
            background-color: rgb(49, 62, 134);
            height: 300px;
        }.item-5 {
            background-color: rgb(230, 99, 99);
            height: 200px;
        }.item-6 {
            background-color: rgb(255, 213, 0);
            height: 300px;
        }.item-7 {
            background-color: rgb(124, 126, 145);
            height: 400px;
        }.item-8 {
            background-color: rgb(169, 199, 38);
            height: 230px;
        }.item-9 {
            background-color: rgb(114, 128, 53);
            height: 300px;
        }.item-10 {
            background-color: rgb(48, 54, 18);
            height: 260px;
        }.item-11 {
            background-color: rgb(104, 115, 43);
            height: 230px;
        }.item-12 {
            background-color: rgb(118, 122, 96);
            height: 240px;
        }.item-13 {
            background-color: rgb(118, 122, 96);
            height: 250px;
        }.item-14 {
            background-color: rgb(118, 122, 96);
            height: 270px;
        }.item-15 {
            background-color: rgb(118, 122, 96);
            height: 330px;
        }.item-16 {
            background-color: rgb(118, 122, 96);
            height: 200px;
        }.item-17 {
            background-color: rgb(118, 122, 96);
            height: 100px;
        }.item-18 {
            background-color: rgb(118, 122, 96);
            height: 400px;
        }.item-19 {
            background-color: rgb(151, 22, 184);
            height: 340px;
        }.item-20 {
            background-color: rgb(118, 122, 96);
            height: 350px;
        }.item-21 {
            background-color: rgb(33, 117, 162);
            height: 360px;
        }.item-22 {
            background-color: rgb(231, 25, 104);
            height: 370px;
        }.item-23 {
            background-color: rgb(231, 25, 104);
            height: 310px;
        }.item-24 {
            background-color: rgb(231, 25, 104);
            height: 970px;
        }
    </style>

<div id="box">
        <div class="item item-1">1</div>
        <div class="item item-2">2</div>
        <div class="item item-3">3</div>
        <div class="item item-4">4</div>
        <div class="item item-5">5</div>
        <div class="item item-6">6</div>
        <div class="item item-7">7</div>
        <div class="item item-8">8</div>
        <div class="item item-9">9</div>
        <div class="item item-10">10</div>
        <div class="item item-11">11</div>
        <div class="item item-12">12</div>
        <div class="item item-13">13</div>
        <div class="item item-14">14</div>
        <div class="item item-15">15</div>
        <div class="item item-16">16</div>
        <div class="item item-17">17</div>
        <div class="item item-18">18</div>
        <div class="item item-19">19</div>
        <div class="item item-20">20</div>
        <div class="item item-21">21</div>
        <div class="item item-22">22</div> 
        <div class="item item-23">23</div> 
        <div class="item item-24">24</div>        
</div>

<script>
    var items = document.getElementsByClassName('item');
    //定义间隙10像素
    var gap = 10;
    //进页面执行函数
    window.onload = function () {
        waterFall();
    }

    function waterFall() {
        //首先确定列数 = 页面的宽度 / 图片的宽度
        var pageWidth = getClient().width;
        var itemWidth = items[0].offsetWidth;
        var columns = parseInt(pageWidth / (itemWidth + gap));
        var arr = [];//定义一个数组，用来存储元素的高度
        for(var i = 0;i < items.length; i++){
            if(i < columns) {
                //满足这个条件则说明在第一行，文章里面有提到
                items[i].style.top = 0;
                items[i].style.left = (itemWidth + gap) * i + 'px';
                arr.push(items[i].offsetHeight);
            }else {
                //其他行，先找出最小高度列，和索引
                //假设最小高度是第一个元素
                var minHeight = arr[0];
                var index = 0;
                for(var j = 0; j < arr.length; j++){//找出最小高度
                   if(minHeight > arr[j]){
                       minHeight = arr[j];
                       index = j;
                   } 
                }
                //设置下一行的第一个盒子的位置
                //top值就是最小列的高度+gap
                items[i].style.top = arr[index] + gap + 'px';
                items[i].style.left = items[index].offsetLeft + 'px';

                //修改最小列的高度
                //最小列的高度 = 当前自己的高度 + 拼接过来的高度 + 间隙的高度
                arr[index] = arr[index] + items[i].offsetHeight + gap;
            }
        }
    }

    //当页面尺寸发生变化时，触发函数，实现响应式
    window.onresize = function () {
        waterFall();
    }

    // clientWidth 处理兼容性
    function getClient() {
        return {
            width: window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth,
            height: window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight
        }
    }
    // scrollTop兼容性处理
    function getScrollTop() {
        return window.pageYOffset || document.documentElement.scrollTop;
    }
</script>