<script lang="ts" setup>
import { capitalize } from '~/utils/str'

// composable
const { t } = useLang()

// compiler macro
definePageMeta({
  layout: 'page',
})
useHead(() => ({
  title: capitalize(t('pages.about.title')),
  meta: [
    {
      name: 'description',
      content: t('pages.about.description'),
    },
  ],
}))
</script>

<template>
  <PageWrapper>
    <PageHeader>
      <PageTitle :text="$t('pages.about.title')" class="capitalize" />
    </PageHeader>
    <PageBody>
      <PageSection>
        <div v-for="i in 7" :key="i" class="text-6xl uppercase">about us</div>
      </PageSection>
    </PageBody>
  </PageWrapper>
</template>
