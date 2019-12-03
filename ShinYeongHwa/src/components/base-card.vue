<template>
    <li>
        <a href="#" :class="$style.inner">
            <!-- <span :class="$style.labels, ${cardslist.labelstype}">{{ cardslist.labelstype }}</span> -->
            <span :class="[
            $style[type],
            $style[cardslist.labelstype]
            ]
            ">{{ cardslist.labelstype }}</span>
            <div :class="$style.thumb_box">
                <img :src="require(`../assets/${cardslist.src}`)" alt="">
            </div>
            <div :class="$style.content_box">
                <strong :class="$style.title">{{ cardslist.maintext }}</strong>
                <p :class="$style.description">{{ cardslist.subtext }}</p>
            </div>
        </a>
    </li>
</template>

<script>
    export default {
        name: 'BaseCard',
        props:{
            cardslist:{
                type: Object,
                default: () => {}
            },
            type: {
                type: String,
                default: 'labels'
            }
            // newType: {
            //     type: String,
            //     default: 'new'
            // }
        }
    }
</script>

<style lang="scss" module>
  
.inner {
position: relative;
display: block;
margin: 0 0 20px 20px;
background: #fff;
color: #000;
text-decoration: none;
}

.thumb_box {
overflow: hidden;
width: 100%;
height: 220px;
vertical-align: top;

&:hover {
    opacity: 0.6;
}

img {
    width: 100%;
}
}
.title {
overflow: hidden;
text-overflow: ellipsis;
white-space: nowrap;
display: block;
margin-bottom: 10px;
font-size: 18px;
font-weight: bold;
}
.content_box {
    padding: 20px 15px 12px;
}
.description {
overflow: hidden;
height: 46px;
margin: 0;
font-size: 15px;
line-height: 22px;
}

.labels {
position: absolute;
top: 0;
left: 0;
z-index: 10;
}
.labels {
display: inline-block;
padding: 5px 10px;
font-size: 12px;
color: #fff;
line-height: 14px;
}

.new {
background: #ff9631;
}

.hot {
background: #f44336;
}
</style>