<div class="card">
  <slot />
</div>

<style>
  .card {
    /* background: rgb(248, 248, 248);
    padding: 20px;
    border-radius: 15px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1); */
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
    /* box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37); */
    backdrop-filter: blur(14.5px);
    -webkit-backdrop-filter: blur(14.5px);
    border-radius: 10px;
    border: 1px solid rgba(255, 255, 255, 0.18);
    padding: 20px;
  }
</style>
