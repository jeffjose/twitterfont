<script>
export let name, src, color, text = "abc", style;

import {onMount} from 'svelte';

onMount(async () => {

  console.log('onMount' + src);

  var style = document.createElement('style');
  style.appendChild(document.createTextNode(`
  @font-face {
    font-family: "${name}";
    src: url('${src}');
  }
  
  `));

  document.head.appendChild(style);

})
</script>

<style>
  .wrapper { 
    grid-column: 1/1;
    grid-row: 1/1;
  }

</style>


<div class="wrapper" style="font-family:{name}, 'Adobe Blank'; font-size: 50pt; color: {color}; align-self: baseline; {style}">
  <div>{text}</div>
</div>
