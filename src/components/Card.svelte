<script>
    import Comments from "./Comments.svelte";
</script>

<div class="Card">
  <div class="Card-container">
    <div class="Card-header">
      <div class="Card-user">
        <img
          src="https://c4.wallpaperflare.com/wallpaper/583/130/505/lea-seydoux-women-blue-eyes-blonde-wallpaper-preview.jpg"
          alt="img.post.loading..." />
        <h2>Emma Blue</h2>
        <span>Marseille, France</span>
      </div>
      <div class="Card-settings">
        <span class="material-icons">more_horiz</span>
      </div>
    </div>
    <div class="Card-photo">
      <figure>
        <img
          src="https://c4.wallpaperflare.com/wallpaper/583/130/505/lea-seydoux-women-blue-eyes-blonde-wallpaper-preview.jpg"
          alt="img.post.loading..." />
      </figure>
    </div>
    <div class="Card-icons">
      <div class="Card-icons-first">
        <span class="material-icons">local_florist</span>
      </div>
      <div class="Card-icons-second">
        <span class="material-icons">share</span>
      </div>
    </div>
    <div class="Card-description">
      <h3>Emma Blue</h3>
      <span>Blue is the warmest colour</span>
    </div>
    <Comments/>
  </div>
</div>
