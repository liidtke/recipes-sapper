<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`recipes.json`).then(r => r.json()).then(posts => {
      return { posts };
    });
  }
</script>

<script>
  import  Featured from '../components/Featured.svelte'
  export let posts;

</script>

<style>
  .home-container {
    align-items: top;
    display: flex;
   
    justify-content: center;
    margin: 2em 0;
    min-height: 200px;
  }

  /* .home-copy {
    flex: 1;
  } */

  h1 {
    font-weight: 600;
    margin-bottom: 0.5em;
  }

  p {
    font-size: 1.4em;
    line-height: 1.5;
  }

  figure {
    margin: 0 1em;
    text-align: center;
  }

  figcaption {
    font-size: .8em;
    font-style: italic;
  }

  img {
    width: 100%;
    max-width: 400px;
  }

  @media (max-width: 1020px) {
    p {
      font-size: 1.2em;
    }

    img {
      max-width: 300px;
    }
  }

  @media (max-width: 800px) {
    .home-container {
      flex-direction: column;
    }

    .home-copy {
      flex: 0;
      padding-bottom: 2em;
      text-align: center;
    }
  }
</style>

<svelte:head>
  <title>Receitas da Sarah</title>
</svelte:head>

<div class="home-container">
  <div class="home-copy">
    <h1>Receitas da Sarah</h1>
    <p>Melhores receitinhas que achei por aí, com meu toque. <a href="/recipes">Ver todas</a> </p>
  </div>

  <figure>
    <img src='/images/uQs1802D0CQ-unsplash.jpg' alt='Imagem de uma cozinha'>
    <!-- <figcaption>Photo by <a href="https://unsplash.com/@florianklauer" target="_blank">Florian Klauer</a> on Unsplash</figcaption> -->
    
  </figure>
  <!-- <figure>
    <img alt='Person typing on laptop' src='undraw-illustration.svg'>
    <figcaption>Illustration thanks to <a href="https://undraw.co" target="_blank">Undraw</a></figcaption>
  </figure> -->
</div>

<Featured bind:posts></Featured>

