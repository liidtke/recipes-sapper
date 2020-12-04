<script>
  import { onMount } from "svelte";

  export let posts;

  onMount(async () => {
    posts.slice(0, 2);
  });
</script>

<style>
 
  p {
    text-align: justify;
  }
</style>

<h2 class="featured">Últimas Receitas</h2>

{#each posts as post, index}
  <div class="post">
    <div class="post-item">
      <h2><a rel="prefetch" href="recipes/{post.slug}">{post.title}</a></h2>
      <p>{post.excerpt}</p>
      <div class="post-item-footer">
        <span class="post-item-date">— {post.printDate}</span>
      </div>
    </div>
  </div>
{/each}
