<template>
  <div id="app">
    <!--
      This is the root of your panel
      Content should go inside this #app element
    -->
    <Panel>
      <HelloWorld msg="Bombino basic" />
    </Panel>
    <Menus refresh debug />
  </div>
</template>

<script>
// Utility components, see here:
// https://github.com/Inventsable/lokney
import { Menus, Panel } from "lokney";

import { evalScript } from "workaround";

/*
  Panel component above also includes:
    - Starlette UI theme and color library: 
      https://github.com/Inventsable/starlette
    - CEP-Spy identification and app utility:
      https://github.com/Inventsable/cep-spy
 These are still installed into this panel and can be used when needed like so:
 import spy from 'cep-spy'

 NOTES: 
  - Starlette is already active in your panel! There's no need to initialize it.
  - Need CSInterface or a script? You can use the script-path attribute of Panel to launch scripts or utilities:
    https://github.com/Inventsable/lokney/tree/master/components/Panel
*/

export default {
  name: "App",
  components: {
    Menus,
    Panel,
    HelloWorld: require("./components/HelloWorld.vue").default,
  },
  mounted() {
    // If you need CEP-Spy:
    let spy = require("cep-spy").default;
    console.log(spy);

    // If you need to run JSX script:
    evalScript(`alert("Hello World")`).then((result) => {
      console.log(result); // This is only relevant if you need to return a value or execute code after the script
    });

    // You can also use async/await, though you'll need the async keyword prefix for mounted() or any particular method using it:
    let someScripting = await evalScript(`alert("I run first")`);
    console.log("I run second, since we're using async/await");
  },
};
</script>

<style>
</style>
