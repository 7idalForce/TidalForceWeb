<script lang="ts" setup>
// composable
const { t } = useLang()

// meta
definePageMeta({
  layout: 'page',
})

useHead({
  title: 'TidalForce | 为庞大世界发展献出绵薄之力',
  meta: [
    {
      name: 'description',
      content: 'To do our bit for this great world, just like the tidal force.',
    },
  ],
})

const titlesText = (str: string) => {
  return t(str).split('[]')
}
</script>

<template>
  <PageWrapper class="flex flex-col flex-1 px-5 gap-5 justify-center lg:px-35">
    <!-- <PageBody class="flex-1 flex"> -->
    <PageSection
      class="flex rounded-7xl flex-1 py-10 mx-7 items-center"
      :style="{
        backgroundImage: `url(https://w.wallhaven.cc/full/qz/wallhaven-qz36xl.jpg)`,
        backgroundSize: 'cover',
        backgroundPosition: 'center',
        backgroundRepeat: 'no-repeat',
      }"
    >
      <div class="flex flex-col flex-1 z-10 md:pl-20 md:w-1/50">
        <h1
          class="flex flex-col mt-4 text-white text-center gap-6 md:text-left"
        >
          <span
            v-for="(item, i) in titlesText('pages.index.title')"
            :key="i"
            class="font-black text-3xl ali drop-shadow-xl block md:text-4xl xl:text-5xl 2xl:text-7xl"
            :class="{
              'text-5xl md:text-6xl xl:text-7xl 2xl:text-8xl': i === 0,
            }"
          >
            <span>{{ item }}</span>
          </span>
        </h1>
        <div class="flex space-x-4 mt-20 justify-center md:justify-start">
          <Button
            size="lg"
            text="Github"
            type="opposite"
            class="font-extrabold"
            href="https://github.com/EE-Wiki"
          />
        </div>
      </div>
    </PageSection>
    <!-- We learnt from waterflames.cn when designing this PageSection. -->
    <!-- </PageBody> -->
  </PageWrapper>
</template>

<style lang="scss">
@import '../assets/sass/variables';

// html.dark {
//   .animated-text-bg {
//     color: theme('colors.gray.100');
//     &:before {
//       color: theme('colors.gray.100');
//     }
//   }
// }
</style>
