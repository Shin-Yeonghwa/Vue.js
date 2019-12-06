<template>
  <BaseLayout>

    <!-- banner -->
    <BaseBanner title="Start something that matters" description="Stop wasting valuable time with projects that just isn't you.">
      <!-- <BaseButton translucence>Learn more and start today</BaseButton>
      <BaseButton whiteOutline>Learn more and start today</BaseButton> -->
      <BaseButton color-type="translucence" :class="$style.banner_button">Learn more and start today</BaseButton>
      <BaseButton color-type="white_outline" :class="$style.banner_button">Learn more and start today</BaseButton>
    </BaseBanner>
    <!-- banner -->

    <div :class="$style.section">
      <BaseTitle title="News" more-url="/about" />
      <BaseList :list-data="thubmListData" thumb-list />
    </div>

    <div :class="$style.section">
      <BaseTitle title="WORK" />
      <BaseTab :list="workTabList" border-type/>
      <BaseList :list-data="postListData" post-list />
    </div>

  </BaseLayout>
</template>

<script>
// @ is an alias to /src
import BaseLayout from '@/components/base-layout'
import BaseBanner from '@/components/base-banner'
import BaseButton from '@/components/base-button'
import BaseTitle from '@/components/base-title'
import BaseList from '@/components/base-list'
import BaseTab from '@/components/base-tab'
import { workTabList, postListData, thubmListData } from '@/mock-data/data.js'

export default {
  name: 'home',
  components: {
    BaseLayout,
    BaseBanner,
    BaseButton,
    BaseTitle,
    BaseList,
    BaseTab
  },
  data() {
    return {
      workTabList,
      postListData,
      thubmListData
    }
  }
}
</script>

<style lang="scss" module>
.banner_button {
  & + .banner_button {
    margin-left: 10px;
  }
}

.section {
  max-width: 1240px;
  margin: 0 auto;
  padding: 30px 0 20px;
}
</style>