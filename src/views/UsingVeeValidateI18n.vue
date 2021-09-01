<template>
  <h2>Using @vee-validate/i18n</h2>
  <p data-v-b816388a="">The <code data-v-b816388a="">@vee-validate/i18n</code> contains a simple message generator function that you can use to generate localized messages from JSON objects:</p>
  <p data-v-b816388a="">First, you need to install the <code data-v-b816388a="">@vee-validate/i18n</code> package:</p>

  <p data-v-b816388a="">import the <code data-v-b816388a="">localize()</code> function from <code data-v-b816388a="">@vee-validate/i18n</code> which returns a message generator function:</p>
<pre>
yarn add @vee-validate/i18n

# or with npm
npm install @vee-validate/i18n
</pre>
<p data-v-b816388a="">import the <code data-v-b816388a="">localize()</code> function from <code data-v-b816388a="">@vee-validate/i18n</code> which returns a message generator function:</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> defineRule<span style="color:#d2cd86; ">,</span> configure <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">vee-validate</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> required <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/rules</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> localize <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// Define the rule globally</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">required</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> required<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  <span style="color:#9999a9; ">// Generates an English message locale generator</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">en</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> <span style="color:#b060b0; ">{</span>
    messages<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      required<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">This field is required</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
    <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>
<p data-v-b816388a="">You can change the locale using <code data-v-b816388a="">setLocale</code> function exported by the <code data-v-b816388a="">@vee-validate/i18n</code> anywhere in your application:</p>


<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> setLocale <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

setLocale<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">ar</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>
<p data-v-b816388a="">To save you a lot of time translating <code data-v-b816388a="">@vee-validate/rules</code> messages to your language, the awesome community around vee-validate already contributed over 40+ languages that you can use directly in your application and get started quickly. The localized files include localized messages for all the <a data-v-b816388a="" href="/v4/guide/global-validators#available-rules" class="">global rules provided by @vee-validate/rules package</a>.</p>
<p data-v-b816388a="">You can import the needed locale from the <code data-v-b816388a="">@vee-validate/i18n/dist/locale/{localeCode}.json</code> and they can be passed directly to the localize function. This snippet adds the English and Arabic localized messages for all the rules of <code data-v-b816388a="">@vee-validate/rules</code> package into the message generator function:</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> configure <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">vee-validate</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> localize <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> en from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n/dist/locale/en.json</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> ar from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n/dist/locale/ar.json</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
    en<span style="color:#d2cd86; ">,</span>
    ar<span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>
    <localizing-field-name />
    <hr />
    <placeholder-interpolation />
    <hr />
    <loading-locale-from-cdn />
</template>

<script>
import LocalizingFieldName from '../components/LocalizingFieldName.vue'
import PlaceholderInterpolation from '../components/PlaceholderInterpolation.vue'
import LoadingLocaleFromCdn from '../components/LoadingLocaleFromCdn.vue'

import { defineRule, configure } from 'vee-validate'
import { required } from '@vee-validate/rules'
import { localize, setLocale } from '@vee-validate/i18n'

// Define the rule globally
defineRule('required', required)

configure({
    generateMessage: localize({
        en: {
            required: 'This field is required',
        },
        ar: {
            required: 'هذا الحقل مطلوب',
        }
    })
})

setLocale('ar');

export default {
    name: 'UsingVeeValidateI18n',
    components: {
        LocalizingFieldName,
        PlaceholderInterpolation,
        LoadingLocaleFromCdn
    }
}
</script>

<style>

</style>