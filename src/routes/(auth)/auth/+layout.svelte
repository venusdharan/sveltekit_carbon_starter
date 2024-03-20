<script>
  import { onMount } from "svelte";
  import "carbon-components-svelte/css/all.css";
  import { Grid, Row, Column, Content } from "carbon-components-svelte";
  let theme = "g100"; // "white" | "g10" | "g80" | "g90" | "g100"
  onMount(function () {
    window.document.documentElement.setAttribute("theme", theme);
  });

  $: theme, changeTheme();

  function changeTheme() {
    if (window.document) {
      window.document.documentElement.setAttribute("theme", theme);
    }
  }
</script>

<Content><Grid><slot /></Grid></Content>
