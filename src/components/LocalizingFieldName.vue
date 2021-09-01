<template>
  <h3>Localizing Field Names</h3>
  <p data-v-b816388a="">To localize the field name with the <code data-v-b816388a="">@vee-validate/i18n</code> package, you can add a <code data-v-b816388a="">names</code> property to your dictionaries containing the translated names of the fields.</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> configure <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">vee-validate</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> localize <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">@vee-validate/i18n</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
    en<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      names<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
        age<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">Age</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
      <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
    <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
    ar<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      age<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">السن</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
    <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>
    <p data-v-b816388a="">Then whenever a message is generated for a global rule, vee-validate will try to match the field name with the <code data-v-b816388a="">names</code> property found in the active locale.</p>


<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> defineRule<span style="color:#d2cd86; ">,</span> Form<span style="color:#d2cd86; ">,</span> Field<span style="color:#d2cd86; ">,</span> ErrorMessage<span style="color:#d2cd86; ">,</span> configure <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidate<span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> required<span style="color:#d2cd86; ">,</span> between<span style="color:#d2cd86; ">,</span> confirmed <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidateRules<span style="color:#b060b0; ">;</span>
<span style="color:#e66170; font-weight:bold; ">const</span> <span style="color:#b060b0; ">{</span> localize<span style="color:#d2cd86; ">,</span> loadLocaleFromURL <span style="color:#b060b0; ">}</span> <span style="color:#d2cd86; ">=</span> VeeValidateI18n<span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// define global rules</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">required</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> required<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">between</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> between<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
defineRule<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">confirmed</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> confirmed<span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// Load locale from URL</span>
loadLocaleFromURL<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">https://unpkg.com/@vee-validate/i18n@4.1.0/dist/locale/ar.json</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>

<span style="color:#9999a9; ">// Activate the locale</span>
configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  generateMessage<span style="color:#b060b0; ">:</span> localize<span style="color:#d2cd86; ">(</span><span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">ar</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span> <span style="color:#b060b0; ">{</span>
    names<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
      name<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">الاسم</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
      age<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">السن</span><span style="color:#02d045; ">'</span><span style="color:#d2cd86; ">,</span>
      ageConfirm<span style="color:#b060b0; ">:</span> <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">تأكيد السن</span><span style="color:#02d045; ">'</span>
    <span style="color:#b060b0; ">}</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span>
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
    <hr />
    <v-form @submit="onSubmit">
        <label for="name">Name</label>
        <v-field name="name" type="text" rules="required"></v-field>
        <error-message name="name"></error-message>
        <br />
        <label for="age">Age</label>
        <v-field name="age" type="number" rules="required|between:18,96"></v-field>
        <error-message name="age"></error-message>
        <br />
        <label for="name">Age Confirm</label>
        <v-field name="ageConfirm" type="number" rules="required|confirmed:@age"></v-field>

        <error-message name="ageConfirm"></error-message>
        <br />
        <button>Submit</button>
    </v-form>
</template>

<script>
import { defineRule, Form, Field, ErrorMessage, configure } from 'vee-validate'
import { required, between, confirmed } from '@vee-validate/rules'
import { localize, loadLocaleFromURL } from '@vee-validate/i18n'

// define global rules
defineRule('required', required);
defineRule('between', between);
defineRule('confirmed', confirmed);

// Load locale from URL
loadLocaleFromURL('https://unpkg.com/@vee-validate/i18n@4.1.0/dist/locale/en.json');

// Activate the locale
configure({
  generateMessage: localize('en', {
    names: {
      name: 'Name',
      age: '',
      ageConfirm: 'Age Confirm'
    }
  })
});

export default {
    name: 'LocalizingFieldName',
    components: {
        // Components were renamed to avoid conflicts of HTML from element without a vue compiler
        VForm: Form,
        VField: Field,
        ErrorMessage: ErrorMessage
    },
    methods: {
        onSubmit(values) {
            alert(JSON.stringify(values, null, 2))
        }
    }
}
</script>

<style>

</style>