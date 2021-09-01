<template>
  <h3>Placeholder Interpolation</h3>
  <p data-v-b816388a="">Your messages can be more complex than <code data-v-b816388a="">required</code>, for example a <code data-v-b816388a="">between</code> rule would need access to the params values to be able to produce a meaningful error message, the <code data-v-b816388a="">@vee-validate/i18n</code> plugin comes with interpolation support for various placeholders, consider this example:</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> defineRule<span style="color:#d2cd86; ">,</span> configure <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">vee-validate</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> between <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/rules</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> localize <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// Define the rule globally</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">between</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> between<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  <span style="color:#9999a9; ">// Generates an English message locale generator</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">en</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> <span style="color:#b060b0; ">{</span>
    messages<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      between<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">The {field} value must be between 0:{min} and 1:{max}</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
    <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> defineRule<span style="color:#d2cd86; ">,</span> Form<span style="color:#d2cd86; ">,</span> Field<span style="color:#d2cd86; ">,</span> ErrorMessage<span style="color:#d2cd86; ">,</span> configure <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidate<span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> required<span style="color:#d2cd86; ">,</span> between<span style="color:#d2cd86; ">,</span> confirmed <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidateRules<span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> localize <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidateI18n<span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// define global rules</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">required</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> required<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">between</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> between<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">confirmed</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> confirmed<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  <span style="color:#9999a9; ">// create and set a localization handler</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">en</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> <span style="color:#b060b0; ">{</span>
    messages<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      <span style="color:#9999a9; ">// interpolates the field name</span>
      required<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">The {field} is required</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
      <span style="color:#9999a9; ">// interpolates the min, max params</span>
      between<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">The {field} value must be between 0:{min}, 1:{max}</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
      <span style="color:#9999a9; ">// Interpolates another field value in the form</span>
      confirmed<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">The {field} value must match {age}</span><span style="color:#02d045; ">'</span>
    <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

<span style="color:#e66170; font-weight:bold; ">const</span> App <span style="color:#d2cd86; ">=</span> <span style="color:#b060b0; ">{</span>
  components<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
    <span style="color:#9999a9; ">// Components were renamed to avoid conflicts of HTML form element without a vue compiler</span>
    VForm<span style="color:#b060b0; ">:</span> Form<span style="color:#d2cd86; ">,</span>
    VField<span style="color:#b060b0; ">:</span> Field<span style="color:#d2cd86; ">,</span>
    ErrorMessage<span style="color:#b060b0; ">:</span> ErrorMessage<span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
  methods<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
    onSubmit<span style="color:#d2cd86; ">(</span>values<span style="color:#d2cd86; ">)</span> <span style="color:#b060b0; ">{</span>
      <span style="color:#e66170; font-weight:bold; ">alert</span><span style="color:#d2cd86; ">(</span>JSON<span style="color:#d2cd86; ">.</span><span style="color:#e66170; font-weight:bold; ">stringify</span><span style="color:#d2cd86; ">(</span>values<span style="color:#d2cd86; ">,</span> <span style="color:#0f4d75; ">null</span> <span style="color:#d2cd86; ">,</span><span style="color:#008c00; ">2</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
    <span style="color:#b060b0; ">}</span>
  <span style="color:#b060b0; ">}</span>
<span style="color:#b060b0; ">}</span>
Vue<span style="color:#d2cd86; ">.</span>createApp<span style="color:#d2cd86; ">(</span>App<span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">.</span>mount<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">#app</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">)</span>
</pre>

</template>

<script>
export default {

}
</script>

<style>

</style>