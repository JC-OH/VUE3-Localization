<template>
  <h1>Localization (i18n)</h1>
  <p data-v-b816388a="">This guide only addresses generating error messages for <a data-v-b816388a="" href="/v4/guide/global-validators" class="">globally defined validators</a> using vee-validate's own <code data-v-b816388a="">@vee-validate/i18n</code> plugin.</p>
  <p data-v-b816388a="">If you are using vee-validate with yup, then you should check out <a data-v-b816388a="" href="https://github.com/jquense/yup#using-a-custom-locale-dictionary" rel="nofollow noopener noreferrer" target="_blank">yup's localization guide</a>. If you are using another library for data validation, check their i18n capabilities.</p>
  <global-message-generator />
  <hr />
  <custom-labels />
  <hr>
  <using-vee-validate-i18n />
</template>

<script>
import UsingVeeValidateI18n from './UsingVeeValidateI18n.vue'
import GlobalMessageGenerator from '../components/GlobalMessageGenerator.vue'
import CustomLabels from '../components/CustomLabels.vue'
export default {
  name: 'Localization',
  components: {
    UsingVeeValidateI18n,
    GlobalMessageGenerator,
    CustomLabels
  }
}
</script>

<style>

</style>