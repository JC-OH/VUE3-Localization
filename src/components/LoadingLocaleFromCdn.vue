<template>
  <h3>Loading Locale From CDN</h3>
  <p data-v-b816388a="">If you are using Vue.js over CDN, you can still load the locale files without having to copy them to your code, the <code data-v-b816388a="">@vee-validate/i18n</code> library exposes a <code data-v-b816388a="">loadLocaleFromURL</code> function that accepts a URL to a locale file.</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#d2cd86; ">&lt;</span>script src<span style="color:#d2cd86; ">=</span><span style="color:#02d045; ">"</span><span style="color:#00c4c4; ">path/to/vee-validate.js</span><span style="color:#02d045; ">"</span><span style="color:#d2cd86; ">&gt;</span><span style="color:#d2cd86; ">&lt;</span><span style="color:#d2cd86; ">/</span>script<span style="color:#d2cd86; ">&gt;</span>
<span style="color:#d2cd86; ">&lt;</span>script src<span style="color:#d2cd86; ">=</span><span style="color:#02d045; ">"</span><span style="color:#00c4c4; ">path/to/@vee-validate/rules.js</span><span style="color:#02d045; ">"</span><span style="color:#d2cd86; ">&gt;</span><span style="color:#d2cd86; ">&lt;</span><span style="color:#d2cd86; ">/</span>script<span style="color:#d2cd86; ">&gt;</span>
<span style="color:#d2cd86; ">&lt;</span>script src<span style="color:#d2cd86; ">=</span><span style="color:#02d045; ">"</span><span style="color:#00c4c4; ">path/to/@vee-validate/i18n.js</span><span style="color:#02d045; ">"</span><span style="color:#d2cd86; ">&gt;</span><span style="color:#d2cd86; ">&lt;</span><span style="color:#d2cd86; ">/</span>script<span style="color:#d2cd86; ">&gt;</span>

<span style="color:#d2cd86; ">&lt;</span>script<span style="color:#d2cd86; ">&gt;</span>
  <span style="color:#9999a9; ">// Install all rules</span>
  Object<span style="color:#d2cd86; ">.</span><span style="color:#e66170; font-weight:bold; ">keys</span><span style="color:#d2cd86; ">(</span>VeeValidateRules<span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">.</span><span style="color:#e66170; font-weight:bold; ">forEach</span><span style="color:#d2cd86; ">(</span>rule <span style="color:#d2cd86; ">=</span><span style="color:#d2cd86; ">&gt;</span> <span style="color:#b060b0; ">{</span>
    VeeValidate<span style="color:#d2cd86; ">.</span>defineRule<span style="color:#d2cd86; ">(</span>rule<span style="color:#d2cd86; ">,</span> VeeValidateRules<span style="color:#d2cd86; ">[</span>rule<span style="color:#d2cd86; ">]</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

  <span style="color:#9999a9; ">// Downloads and merges the locale from URL</span>
  VeeValidateI18n<span style="color:#d2cd86; ">.</span>loadLocaleFromURL<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">https://unpkg.com/@vee-validate/i18n@4.0.2/dist/locale/ar.json</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

  <span style="color:#9999a9; ">// Activate the locale</span>
  VeeValidate<span style="color:#d2cd86; ">.</span>configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
    generateMessage<span style="color:#b060b0; ">:</span> VeeValidateI18n<span style="color:#d2cd86; ">.</span>localize<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">ar</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
<span style="color:#d2cd86; ">&lt;</span><span style="color:#d2cd86; ">/</span>script<span style="color:#d2cd86; ">&gt;</span>
</pre>

</template>

<script>
export default {

}
</script>

<style>

</style>