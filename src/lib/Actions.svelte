<script>
    import {
    HeaderAction,
    HeaderPanelLinks,
    HeaderPanelDivider,
    HeaderPanelLink
  } from "carbon-components-svelte";
let isOpen = false;
</script>

<HeaderAction bind:isOpen >
    <HeaderPanelLinks>
      <HeaderPanelDivider>Switcher subject 1</HeaderPanelDivider>
      <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
      <HeaderPanelDivider>Switcher subject 2</HeaderPanelDivider>
      <HeaderPanelLink>Switcher item 1</HeaderPanelLink>
      <HeaderPanelLink>Switcher item 2</HeaderPanelLink>
      <HeaderPanelLink>Switcher item 3</HeaderPanelLink>
      <HeaderPanelLink>Switcher item 4</HeaderPanelLink>
      <HeaderPanelLink>Switcher item 5</HeaderPanelLink>
    </HeaderPanelLinks>
</HeaderAction>