<script>
    import * as m from '$lib/paraglide/messages.js';
    import {onMount} from "svelte";
    import {languageTag} from "$lib/paraglide/runtime.js";

    onMount(() => {
        console.log('onMount', languageTag())
    })
</script>

{m.hello()}

<a href="/timer">Timer</a>

