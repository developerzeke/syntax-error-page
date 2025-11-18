<script lang="ts">
  import './style.css';
  import {onNavigate} from '$app/navigation';

  let {data, children} = $props();

  onNavigate(async (navigation) => {
    if (!document.startViewTransition) return;

    return new Promise((oldStateCaptureResolve) => {
      document.startViewTransition(async () => {
        oldStateCaptureResolve();
        await navigation.complete;
      });
    });
  });
</script>

<div class={'theme-dark theme-wrapper'}>
    <main
            id="main-content"
            class="page-layout layout zone"
    >
        {@render children?.()}
    </main>
</div>

<style lang="postcss">
    :global(.theme-wrapper) {
        --bg-root: var(--bg);
        --fg-root: var(--fg);
        min-height: 100vh;
        border-top: var(--border);
        border-color: var(--primary);
        max-width: 85%;
        margin-left: auto;
        margin-right: auto;
    }

    .page-layout {
        margin: 0 auto;
    }

    @media (min-width: 1280px) {
        .page-layout {
            grid-auto-flow: column;
            grid-template-rows: 1fr;
        }
    }
</style>
