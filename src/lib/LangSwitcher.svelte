<script>
    import {i18n} from '$lib/i18n';
    import {page} from '$app/stores';
    import {availableLanguageTags, languageTag} from '$lib/paraglide/runtime.js';
</script>

<ul>
    {#each availableLanguageTags as lang}
        <!-- anchors attribute 'href' for disabled js browser -->
        <li>
            <a
                    href={i18n.route($page.url.pathname)}
                    hreflang={lang}
                    aria-current={lang === languageTag() ? 'page' : undefined}
            >
                {lang.toLocaleUpperCase()}
            </a>
        </li>
    {/each}
</ul>

<style>
    ul {
        position: fixed;
        z-index: 1;
        inset-block-start: 0;
        inset-inline-end: 1rem;

        display: flex;
        gap: 1rem;

        li {
            list-style-type: none;

            a {
                font-size: 2rem;

                &[aria-current='page'],
                &:hover {
                    color: var(--color-primary);
                }
            }
        }
    }

    @media (prefers-reduced-motion: no-preference) {
        a {
            transition: color 0.25s;
        }
    }
</style>
