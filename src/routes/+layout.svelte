<script>
    import {ParaglideJS} from '@inlang/paraglide-sveltekit';
    import {i18n} from '$lib/i18n';
    import LangSwitcher from '$lib/LangSwitcher.svelte';

    const {children} = $props();
</script>

<svelte:options runes={true}/>

<ParaglideJS {i18n}>
    <LangSwitcher />
    {@render children()}
</ParaglideJS>
