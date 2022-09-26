<script lang="ts">
  import Hashtag from '$lib/components/Hashtag.svelte'
  import * as prismicH from '@prismicio/helpers'

  export let squadTitle: []
  export let sprintTitle: string
  export let squadpageUrl: string
</script>

<section>
  <div class="sprint-image">
    <div class="squad-title">
      {@html prismicH.asHTML(squadTitle)}
    </div>
    <div class="sprint-title">
      <h2>Sprint {sprintTitle}</h2>
    </div>
  </div>
  <div class="sprint-components">
    <div class="hastag-container">
      <Hashtag />
    </div>
    <div class="cta-container">
      <a href={squadpageUrl} target="_blank" rel="noreferrer noopener">
        <span>Bekijk</span>
        <span>Squadpage</span>
      </a>
    </div>
  </div>
</section>

<style>
  section {
    min-width: 35rem;
    scroll-snap-align: center;
  }

  @media (max-width: 35rem) {
    section {
      min-width: 90vw;
    }
  }

  .sprint-image {
    background-image: url('/assets/images/your-tribe.avif');
    position: relative;
    height: 22.5rem;
    width: 100%;
    background-size: cover;
    background-position: center 10%;
    border-radius: var(--rounded);
  }

  .squad-title {
    position: absolute;
    top: 0;
    right: 0;
    padding: 0 0 0.75rem 0.75rem;
    background-color: var(--blueberry);
    border-bottom-left-radius: 0.625rem;
  }

  .squad-title::before {
    content: '';
    position: absolute;
    top: 0;
    left: calc(-1 * var(--rounded));
    box-shadow: 0 calc(-1 * var(--rounded)) 0 0 var(--blueberry);
    width: var(--rounded);
    height: calc(2 * var(--rounded));
    border-top-right-radius: var(--rounded);
    background-color: transparent;
  }

  .squad-title::after {
    content: '';
    position: absolute;
    right: calc(-1 * var(--rounded));
    box-shadow: 0 calc(-1 * var(--rounded)) 0 0 var(--blueberry);
    width: var(--rounded);
    height: calc(2 * var(--rounded));
    border-top-right-radius: var(--rounded);
    background-color: transparent;
    bottom: 0;
    transform: translate(-100%, 100%);
  }
  .squad-title :global(h2) {
    color: var(--blueberry);
    background-color: var(--turquoise);
    padding: 0.75rem 0.75rem;
    border-radius: 0.625rem;
    font-size: 1.25rem;
    margin: 0;
  }

  .sprint-title {
    position: absolute;
    bottom: 0;
    left: 0;
    background-color: var(--blueberry);
    padding: 0.75rem 0.75rem 0 0;
    border-top-right-radius: var(--rounded);
  }

  .sprint-title h2 {
    color: var(--turquoise);
    border: 1px solid var(--turquoise);
    padding: 0.75rem 0.75rem;
    border-radius: 0.625rem;
    font-size: 1.25rem;
    margin: 0;
  }

  .sprint-title:before {
    content: '';
    position: absolute;
    background-color: transparent;
    width: 0.5rem;
    height: calc(2 * var(--rounded));
    border-bottom-left-radius: var(--rounded);
    top: calc(-2 * var(--rounded));
    left: 0;
    box-shadow: 0 var(--rounded) 0 0 var(--blueberry);
  }

  .sprint-title:after {
    content: '';
    position: absolute;
    background-color: transparent;
    width: 0.5rem;
    height: calc(2 * var(--rounded));
    border-bottom-left-radius: var(--rounded);
    right: calc(-1 * var(--rounded));
    bottom: 0;
    box-shadow: 0 var(--rounded) 0 0 var(--blueberry);
  }

  .sprint-components {
    display: flex;
    flex-direction: row;
    margin: 1rem 0;
    grid-row: 2;
    gap: 0.75rem;
  }

  .hastag-container {
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1rem;
    background-color: var(--lavender);
  }

  .cta-container {
    flex: 1;
    border-radius: 3.125rem;
    border: 2px solid var(--lavender);
    position: relative;
  }

  .cta-container:hover::after {
    transform: translate(calc(100% - 0.5rem), -50%);
  }

  .cta-container:hover span:first-child {
    color: var(--color-white);
  }

  .cta-container:hover span:last-child {
    color: var(--blueberry);
  }

  .cta-container a {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 0;
    text-decoration: none;
  }

  .cta-container span {
    font-size: 1.2rem;
    width: 50%;
    text-align: center;
    transition: 400ms color ease-in-out;
  }

  .cta-container span:first-child {
    color: var(--blueberry);
  }

  .cta-container span:last-child {
    color: var(--color-white);
  }

  .cta-container::after {
    content: '';
    position: absolute;
    width: 50%;
    height: calc(100% - 0.5rem);
    background-color: var(--color-white);
    top: 50%;
    left: 0.25rem;
    border-radius: var(--pilled);
    transform: translateY(-50%);
    z-index: -1;
    transition: 400ms transform ease-out;
  }
</style>
