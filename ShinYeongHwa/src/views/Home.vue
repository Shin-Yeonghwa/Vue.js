<template>
  <BaseLayout>
      <BaseBanner 
        title="이건 타이틀이야" 
        description="이건 설명 글이야">
        <BaseButton >버튼입니다.</BaseButton>
        <BaseButton colorType="white_outline">버튼입니다.</BaseButton>
      </BaseBanner>
      
      <div :class="$style.section">
        <ul :class="$style.thumb_list">
          <BaseCard 
            v-for="(item,index) in cardslist"
            :key="index"
            :cardslist="item"
            :class="$style.item"
            >
          </BaseCard>
        </ul>
      </div>
      
      <BaseTab :lists="contentslist" type="tab_border"></BaseTab>
      
      <div :class="$style.section">
        <ul :class="$style.post_list">
          <BaseCard 
              v-for="(item,index) in cardslist"
              :key="index"
              :cardslist="item"
              :class="$style.item"
              >
            </BaseCard>
        </ul>
      </div>
  </BaseLayout>
</template>

<script>

// @ is an alias to /src
import BaseLayout from '@/components/base-layout'
import BaseBanner from '@/components/base-banner'
import BaseButton from '@/components/base-button'
import BaseTab from '@/components/base-tab'
import BaseCard from '@/components/base-card'


const contentslist = [
    {
        text: 'Tab1',
        href: '/Tab1'
    },
    {
        text: 'Tab2',
        href: '/Tab2'
    },
    {
        text: 'Tab3',
        href: '/Tab3'
    },
    {
        text: 'Tab3',
        href: '/Tab4'
    },
];


const cardslist = [
    {
        src: 'p1.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.',
        labelstype: 'hot'
    },
    {
        src: 'p2.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'Praesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.',
        labelstype: 'new'
    },
    {
        src: 'p3.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb',
        labelstype: 'hot'
    },
    {
        src: 'p4.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb',
        labelstype: 'new'
    },
    {
        src: 'p5.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb',
        labelstype: 'new'
    },
    {
        src: 'p6.jpg',
        maintext: 'Lorem IpsumLorem IpsumLorem IpsumLorem IpsumLorem Ipsum',
        subtext: 'bPraesent tincidunt sed tellus ut rutrum. Sed vitae justo condimentum, porta lectus vitae, ultricies congue gravida diam non fringilla.bb',
        labelstype: 'new'
    },
];


export default {
  name: 'home',
  components: {
    BaseLayout,
    BaseBanner,
    BaseButton,
    BaseTab,
    BaseCard
  },
  data(){
    return{
      contentslist,
      cardslist
    }
  }
}
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
}

.thumb_list{
  .item {
    width: 33.3333%;
    padding: 0;
    box-sizing: border-box;
  }
}

  
// list2
.post_list {
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
    &+.info::before {
      content: '';
      display: inline-block;
      height: 12px;
      margin: 3px 10px 0 0;
      border-left: 1px solid #999;
      vertical-align: top;
    }
  }
}
  </style>