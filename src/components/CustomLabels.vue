<template>
  <h2>Custom Labels</h2>
  <p data-v-b816388a="">If you want to display different field names in your error messages, the <code data-v-b816388a="">&lt;Field /&gt;</code> component accepts a <code data-v-b816388a="">label</code> prop which allows you to display better names for your fields in their generated messages. Here is an example:</p>
  
<pre style="color:#d1d1d1;background:#000000;"><span style="color:#ff8906; ">&lt;</span><span style="color:#e66170; font-weight:bold; ">Form</span><span style="color:#ff8906; ">&gt;</span>
  <span style="color:#ff8906; ">&lt;</span><span style="color:#f6c1d0; ">Field</span> name<span style="color:#d2cd86; ">=</span><span style="color:#00c4c4; ">"_bad_field_name"</span> label<span style="color:#d2cd86; ">=</span><span style="color:#00c4c4; ">"nice name"</span> rules<span style="color:#d2cd86; ">=</span><span style="color:#00c4c4; ">"required|email"</span> <span style="color:#ff8906; ">/&gt;</span>
  <span style="color:#ff8906; ">&lt;</span><span style="color:#f6c1d0; ">ErrorMessage</span> name<span style="color:#d2cd86; ">=</span><span style="color:#00c4c4; ">"_bad_field_name"</span> <span style="color:#ff8906; ">/&gt;</span>
<span style="color:#ff8906; ">&lt;/</span><span style="color:#e66170; font-weight:bold; ">Form</span><span style="color:#ff8906; ">&gt;</span>
</pre>

  <p data-v-b816388a="">The generated message will use <code data-v-b816388a="">nice name</code> instead of the badly formatted one.</p>
</template>

<script>
export default {

}
</script>

<style>

</style>