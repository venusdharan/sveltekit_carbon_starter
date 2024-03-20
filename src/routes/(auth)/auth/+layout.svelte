<script>
  import { onMount } from "svelte";
  import "carbon-components-svelte/css/all.css";
  import {
    Header,
    HeaderGlobalAction,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    HeaderUtilities,
    SkipToContent
  } from "carbon-components-svelte";
  import { Grid, Row, Column, Content } from "carbon-components-svelte";
  import ThemeSwitcher from "$lib/ThemeSwitcher.svelte";
  onMount(function () {
  

  });

  // $: theme, changeTheme();


</script>
<!--
  company="IBM" platformName="Carbon Svelte"
-->
<Header  >
  <svelte:fragment slot="skip-to-content">
    <SkipToContent />
  </svelte:fragment>
  <HeaderUtilities>
  <ThemeSwitcher/>
</HeaderUtilities>

</Header>

<Content><Grid><slot /></Grid></Content>
