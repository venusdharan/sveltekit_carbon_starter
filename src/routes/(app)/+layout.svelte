<script>
    import { onMount } from "svelte";
    import "carbon-components-svelte/css/all.css";
    import {
        Header,
        HeaderUtilities,
        HeaderAction,
        HeaderPanelLinks,
        HeaderPanelDivider,
        HeaderPanelLink,
        HeaderNav,
        HeaderNavItem,
        HeaderNavMenu,
        HeaderSearch,
        HeaderGlobalAction,
        SideNav,
        SideNavItems,
        SideNavMenu,
        SideNavMenuItem,
        SideNavLink,
        SkipToContent,
        Content,
        Grid,
        Row,
        Column,
        TileGroup,
        RadioTile,
        Button,
    } from "carbon-components-svelte";
    import { expoIn } from "svelte/easing";
    let theme = "g100"; // "white" | "g10" | "g80" | "g90" | "g100"
    onMount(function () {
        // window.document.documentElement.setAttribute("theme", theme);
    });

    // $: theme, changeTheme();

    // function changeTheme() {
    //     if (window.document) {
    //         window.document.documentElement.setAttribute("theme", theme);
    //     }
    // }

    let isSideNavOpen = false;

    import Search from "$lib/Search.svelte";
    import Actions from "$lib/Actions.svelte";
    import Logout from "carbon-icons-svelte/lib/Logout.svelte";
  import SettingsAdjust from "carbon-icons-svelte/lib/SettingsAdjust.svelte";
  import UserAvatarFilledAlt from "carbon-icons-svelte/lib/UserAvatarFilledAlt.svelte";

  import ThemeSwitcher from "$lib/ThemeSwitcher.svelte";

</script>

<Header
    company="Triophore"
    platformName="UI StarterKit"
    bind:isSideNavOpen
    persistentHamburgerMenu={true}
>
    <svelte:fragment slot="skip-to-content">
        <SkipToContent />
    </svelte:fragment>
    <HeaderUtilities>

        <Search />
        <HeaderGlobalAction iconDescription="Profile" icon={UserAvatarFilledAlt} />
        <HeaderGlobalAction
          iconDescription="Log out"
          tooltipAlignment="end"
          icon={Logout}
        />
        <ThemeSwitcher/>
        <Actions />
    </HeaderUtilities>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
    <SideNavItems>
        <SideNavLink text="Link 1" />
        <SideNavLink text="Link 2" />
        <SideNavLink text="Link 3" />
        <SideNavMenu text="Menu">
            <SideNavMenuItem href="/" text="Link 1" />
            <SideNavMenuItem href="/" text="Link 2" />
            <SideNavMenuItem href="/" text="Link 3" />
        </SideNavMenu>
    </SideNavItems>
</SideNav>

<Content>
    <slot />
</Content>
