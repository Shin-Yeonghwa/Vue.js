<template>
  <BaseLayout>
    <BaseBanner title="이건 타이틀이야" description="이건 설명 글이야">
      <BaseButton>버튼입니다.</BaseButton>
      <BaseButton colorType="white_outline">버튼입니다.</BaseButton>
    </BaseBanner>
    <div :class="$style.section">
      <BaseTitle>이미지 리스트</BaseTitle>
      <ul :class="$style.thumb_list">
        <BaseCard
          v-for="(item,index) in cardslist"
          :key="index"
          :cardslist="item"
          :class="$style.item"
        ></BaseCard>
      </ul>
    </div>
    <BaseTab :lists="contentslist" type="tab_border"></BaseTab>
    <div :class="$style.section">
      <BaseTitle>포스트 이미지 리스트</BaseTitle>
      <ul :class="$style.post_list">
        <BasePostCard
          v-for="(item,index) in postcardslist"
          :key="index"
          :postcardslist="item"
          :class="$style.item"
        ></BasePostCard>
      </ul>
    </div>
  </BaseLayout>
</template>

<script>
// @ is an alias to /src
import BaseLayout from "@/components/base-layout";
import BaseBanner from "@/components/base-banner";
import BaseButton from "@/components/base-button";
import BaseTab from "@/components/base-tab";
import BaseCard from "@/components/base-card";
import BasePostCard from "@/components/base-postcard";
import BaseTitle from "@/components/base-title";

const contentslist = [
  {
    text: "Tab1",
    href: "/Tab1"
  },
  {
    text: "Tab2",
    href: "/Tab2"
  },
  {
    text: "Tab3",
    href: "/Tab3"
  },
  {
    text: "Tab3",
    href: "/Tab4"
  }
];

const cardslist = [
  {
    src: "p1.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.",
    labelstype: "hot"
  },
  {
    src: "p2.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.",
    labelstype: "new"
  },
  {
    src: "p3.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    labelstype: "hot"
  },
  {
    src: "p4.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    labelstype: "new"
  },
  {
    src: "p5.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    labelstype: "new"
  },
  {
    src: "p6.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    labelstype: "new"
  }
];

const postcardslist = [
  {
    src: "p1.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.",
    date: "2019.03.23.",
    num: "200"
  },
  {
    src: "p2.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.",
    date: "2019.03.23.",
    num: "200"
  },
  {
    src: "p3.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    date: "2019.03.23.",
    num: "200"
  },
  {
    src: "p4.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    date: "2019.03.23.",
    num: "200"
  },
  {
    src: "p5.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    date: "2019.03.23.",
    num: "200"
  },
  {
    src: "p6.jpg",
    maintext: "Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum",
    subtext:
      "bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb",
    date: "2019.03.23.",
    num: "200"
  }
];

export default {
  name: "home",
  components: {
    BaseLayout,
    BaseBanner,
    BaseButton,
    BaseTab,
    BaseCard,
    BasePostCard,
    BaseTitle
  },
  data() {
    return {
      contentslist,
      cardslist,
      postcardslist
    };
  }
};
</script>


<style lang="scss" module>
.section {
  max-width: 1240px;
  margin: 0 auto;
  padding: 30px 0 20px;
}
.thumb_list {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  flex-wrap: wrap;
  margin-left: -20px;
  .item {
    width: 33.3333%;
    padding: 0;
    box-sizing: border-box;
  }
}
.post_list {
  .item {
    overflow: hidden;
    position: relative;
    padding-bottom: 20px;
    margin-bottom: 20px;
    box-sizing: border-box;
    border-bottom: 1px solid #d5d5d5;
  }
}
</style>