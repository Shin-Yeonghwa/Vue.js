<template>
  <li>
    <a href="#" :class="$style.inner">
      <div :class="$style.thumb_box">
        <img :src="require(`../assets/${postcardslist.src}`)" alt />
      </div>
      <div :class="$style.content_box">
        <strong :class="$style.title">{{ postcardslist.maintext }}</strong>
        <p :class="$style.description">{{ postcardslist.subtext }}</p>
        <div :class="$style.info_box">
          <span :class="$style.info">{{ postcardslist.date}}</span>
          <span :class="$style.info">
            댓글
            <span>{{ postcardslist.num}}</span>
          </span>
        </div>
      </div>
    </a>
  </li>
</template>

<script>
export default {
  name: "BasePostCard",
  props: {
    postcardslist: {
      type: Object,
      default: () => {}
    }
  }
};
</script>

<style lang="scss" module>
.item {
  overflow: hidden;
  position: relative;
  padding-bottom: 20px;
  margin-bottom: 20px;
  box-sizing: border-box;
  border-bottom: 1px solid #d5d5d5;
}

.inner {
  text-decoration: none;
}

.thumb_box {
  float: right;
  width: 210px;
  height: 167px;

  img {
    width: 100%;
    height: 100%;
  }
}

.content_box {
  overflow: hidden;
  padding-right: 25px;
}

.title {
  display: block;
  padding: 15px 0 14px;
  font-size: 20px;
  color: #000;
}

.description {
  margin: 0;
  font-size: 16px;
  line-height: 24px;
  color: #000;
}

.info_box {
  margin-top: 20px;
  line-height: 20px;
  font-size: 13px;
  color: #999;
}

.info {
  display: inline-block;
  margin-right: 6px;
  vertical-align: top;
  & + .info::before {
    content: "";
    display: inline-block;
    height: 12px;
    margin: 3px 10px 0 0;
    border-left: 1px solid #999;
    vertical-align: top;
  }
}
</style>