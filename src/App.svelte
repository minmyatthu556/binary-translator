<script>
  import Bte from './components/BTE.svelte';
  import Etb from './components/ETB.svelte';
  import Footer from './components/Footer.svelte';
  import Header from './components/Header.svelte';
  import Tabs from './shared/Tabs.svelte';

  let items = ['Binary to English', 'English to Binary'];
  let activeItem = 'Binary to English';

  const tabChange = (e) => {
    activeItem = e.detail;
  };
</script>

<Header />
<main>
  <Tabs {items} {activeItem} on:tabChange={tabChange} />

  {#if activeItem === 'Binary to English'}
    <div class="component"><Bte /></div>
  {:else if activeItem === 'English to Binary'}
    <div class="component"><Etb /></div>
  {/if}
</main>

<Footer />

<style>
  .component {
    width: max-content;
    margin: auto;
  }

  @media only screen and (max-width: 360px){
    main {
      max-width: fit-content;
      margin: 20px auto;
    }
  }
</style>
