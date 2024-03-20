<script>
    import { onMount } from "svelte";
    import Incomplete from "carbon-icons-svelte/lib/Incomplete.svelte";
    import { HeaderGlobalAction } from "carbon-components-svelte";
    let theme = "g100"; // "white" | "g10" | "g80" | "g90" | "g100"
    let curr_theme = null;
    onMount(function () {
        if (!window.localStorage) {
            window.document.documentElement.setAttribute("theme", theme);
        }
        if (window.localStorage.getItem("theme")) {
            curr_theme = window.localStorage.getItem("theme");
            if (curr_theme) {
                window.document.documentElement.setAttribute(
                    "theme",
                    curr_theme,
                );
            } else {
                window.document.documentElement.setAttribute("theme", theme);
            }
        } else {
            window.document.documentElement.setAttribute("theme", theme);
        }
    });

    // $: theme, changeTheme();

    function changeTheme() {
        if (window.document) {
            window.document.documentElement.setAttribute("theme", theme);
        }
    }

    function toggleTheme() {
        if (!window.localStorage) {
            window.document.documentElement.setAttribute("theme", theme);
            return;
        }

        if (curr_theme != null) {
            if (curr_theme == "white") {
                curr_theme = "g100";
                window.localStorage.setItem("theme", curr_theme);
                window.document.documentElement.setAttribute(
                    "theme",
                    curr_theme,
                );
            } else {
                curr_theme = "white";
                window.localStorage.setItem("theme", curr_theme);
                window.document.documentElement.setAttribute(
                    "theme",
                    curr_theme,
                );
            }
        }
    }
</script>


<HeaderGlobalAction
iconDescription="Toggle Theme"
tooltipAlignment="end"
icon={Incomplete}
on:click={toggleTheme}
/>