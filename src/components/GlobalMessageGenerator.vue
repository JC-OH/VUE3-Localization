<template>
  <h2>Global Message Generator</h2>
  <p data-v-b816388a="">vee-validate exposes a global config called <code data-v-b816388a="">generateMessage</code> which is a function that should return a string. Whenever any globally defined rule returns a falsy value the <code data-v-b816388a="">generateMessage</code> will be called and its result will be used as an error message for that rule.</p>
  <p data-v-b816388a="">The message generator function has the following type:</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">interface</span> FieldContext <span style="color:#b060b0; ">{</span>
  field<span style="color:#b060b0; ">:</span> string<span style="color:#b060b0; ">;</span> <span style="color:#9999a9; ">// The field's name or label (see next section)</span>
  value<span style="color:#b060b0; ">:</span> any<span style="color:#b060b0; ">;</span> <span style="color:#9999a9; ">// the field's current value</span>
  form<span style="color:#b060b0; ">:</span> Record<span style="color:#d2cd86; ">&lt;</span>string<span style="color:#d2cd86; ">,</span> any<span style="color:#d2cd86; ">&gt;</span><span style="color:#b060b0; ">;</span> <span style="color:#9999a9; ">// other values in the form</span>
  rule<span style="color:#b060b0; ">:</span> <span style="color:#b060b0; ">{</span>
    name<span style="color:#b060b0; ">:</span> string<span style="color:#b060b0; ">;</span> <span style="color:#9999a9; ">//the rule name</span>
    params<span style="color:#b060b0; ">?</span><span style="color:#b060b0; ">:</span> any<span style="color:#d2cd86; ">[</span><span style="color:#d2cd86; ">]</span><span style="color:#b060b0; ">;</span> <span style="color:#9999a9; ">// any params sent to it</span>
  <span style="color:#b060b0; ">}</span><span style="color:#b060b0; ">;</span>
<span style="color:#b060b0; ">}</span>

type ValidationgenerateMessage <span style="color:#d2cd86; ">=</span> <span style="color:#d2cd86; ">(</span>ctx<span style="color:#b060b0; ">:</span> FieldContext<span style="color:#d2cd86; ">)</span> <span style="color:#d2cd86; ">=</span><span style="color:#d2cd86; ">&gt;</span> string<span style="color:#b060b0; ">;</span>
</pre>
    <p data-v-b816388a="">With this information, you could create message handlers with any kind of 3rd party libraries. To register a message generator use the <code data-v-b816388a="">configure</code> function exposed by vee-validate:</p>

<pre style="color:#d1d1d1;background:#000000;"><span style="color:#e66170; font-weight:bold; ">import</span> <span style="color:#b060b0; ">{</span> configure <span style="color:#b060b0; ">}</span> from <span style="color:#02d045; ">'</span><span style="color:#00c4c4; ">vee-validate</span><span style="color:#02d045; ">'</span><span style="color:#b060b0; ">;</span>

configure<span style="color:#d2cd86; ">(</span><span style="color:#b060b0; ">{</span>
  generateMessage<span style="color:#b060b0; ">:</span> context <span style="color:#d2cd86; ">=</span><span style="color:#d2cd86; ">&gt;</span> <span style="color:#b060b0; ">{</span>
    <span style="color:#e66170; font-weight:bold; ">return</span><span style="color:#02d045; "> `</span><span style="color:#00c4c4; ">The field </span><span style="color:#02d045; ">${</span><span style="color:#00c4c4; ">context</span><span style="color:#d2cd86; ">.</span><span style="color:#00c4c4; ">field</span><span style="color:#02d045; ">}</span><span style="color:#00c4c4; "> is invalid</span><span style="color:#02d045; ">`</span><span style="color:#b060b0; ">;</span>
  <span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">,</span>
<span style="color:#b060b0; ">}</span><span style="color:#d2cd86; ">)</span><span style="color:#b060b0; ">;</span>
</pre>

</template>

<script>
import { configure } from 'vee-validate'

export default {
    name: 'GlobalMessageGenerator',
    mounted () {
        const messageHandler = configure({
            generateMessage: context => {
                return `The field ${context.field} is invalid`;
            }
        })

        console.log(messageHandler)
    }
}
</script>

<style>

</style>