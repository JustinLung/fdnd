<script lang="ts">
  import '../styles/theme.css'
  import '../styles/style.css'

  import Header from '$lib/components/Header.svelte'
  import Footer from '$lib/components/Footer.svelte'
</script>

<svelte:head>
  <link
    href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap"
    rel="stylesheet"
  />
</svelte:head>

<Header />
<main>
  <slot />
</main>
<Footer />

<style>
  @media (max-width: 80rem) {
    main {
      padding: 1rem;
    }
  }
</style>
