<script>
  import Comments from "./Comments.svelte";
  import Modal from "./Modal.svelte";
  import { blur } from "svelte/transition";
  import Share from "./Share.svelte";
  import { flowersCount } from "../store/store.js";
  import { likeCount } from "../store/store.js";

  export let username;
  export let location;
  // export let photo;
  export let postComment;
  export let comments;
  export let avatar;

  let isModal = false;
  let isFlowered = false;

  function handleClick() {
    isModal = !isModal;
  }
  function handleFlower() {
    isFlowered = !isFlowered;
    if (isFlowered) {
      $flowersCount++;
    } else {
      $flowersCount--;
    }
  }
</script>

<style>
  .Card {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    background-color: white;
    margin: 0 0 2em 0;
  }
  .Card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
  }
  .Card-user {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
  .Card-user img {
    width: 32px;
    height: 32px;
    border-radius: 50%;
  }
  .Profile-avatar img {
    width: 42px;
    height: 42px;
    border-radius: 50%;
  }
  .Profile-info {
    margin: 0 0 0 0.5em;
  }
  .Profile-info h2 {
    font-size: 14px;
    color: black;
    margin: 0;
    padding: 0;
  }
  .Profile-info span {
    font-size: 12px;
    font-weight: normal;
  }
  .Card-photo {
    padding: 0;
    margin: 0;
  }
  .Card-photo img {
    width: 100%;
    height: auto;
  }
  .Card-photo figure {
    margin: 0;
    padding: 0;
    cursor: pointer;
  }
  .Card-settings i {
    cursor: pointer;
  }
  .Card-icons {
    padding: 1em;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Card-icons i {
    margin: 0 1em 0 0;
    cursor: pointer;
    font-size: 20px;
  }
  .Card-icons i:last-child {
    margin: 0;
  }
  .Card-description {
    padding: 0 1em 1em 1em;
  }
  .Card-description h3 {
    font-size: 14px;
    font-weight: bold;
    color: black;
  }
  .Card-description span {
    font-size: 14px;
  }
  .active-like {
    color: #63cdd7;
    animation: bounce linear 0.8s;
    animation-iteration-count: 1;
    transform-origin: 20% 20%;
  }

  @keyframes bounce {
    0% {
      transform: translate(0px, 0px);
    }
    15% {
      transform: translate(0px, -25px);
    }
    30% {
      transform: translate(0px, 0px);
    }
    45% {
      transform: translate(0px, -15px);
    }
    60% {
      transform: translate(0px, 0px);
    }
    75% {
      transform: translate(0px, -5px);
    }
    100% {
      transform: translate(0px, 0px);
    }
  }
</style>

<div class="Card">
  {#if isModal}
    <div transition:blur>
      <Modal>
        <Share on:click={handleClick} />
      </Modal>
    </div>
  {/if}

  <div class="Card-container">
    <div class="Card-header">
      <div class="Card-user">
        <div class="Profile-avatar">
          <img src={avatar} alt={username} />
          <!-- <img
            src="https://c4.wallpaperflare.com/wallpaper/583/130/505/lea-seydoux-women-blue-eyes-blonde-wallpaper-preview.jpg"
            alt="profile-img" /> -->
        </div>
        <div class="Profile-info">
          <h2>{username}</h2>
          <span>{location}</span>
          <!-- <span>Lea Seydoux</span> -->
        </div>
      </div>
      <div class="Card-settings">
        <i class="material-icons">more_horiz</i>
      </div>
    </div>
    <div class="Card-photo">
      <figure on:dblclick={handleFlower}>
        <!-- <img src={photo} alt={username} /> -->
        <img
          src="https://c4.wallpaperflare.com/wallpaper/583/130/505/lea-seydoux-women-blue-eyes-blonde-wallpaper-preview.jpg"
          alt="img.post.loading..." />
      </figure>
    </div>
    <div class="Card-icons">
      <div
        class="Card-icons-first"
        on:click={handleFlower}
        class:active-like={isFlowered}>
        <i class="material-icons">local_florist</i>
      </div>
      <div class="Card-icons-second" on:click={handleClick}>
        <i class="material-icons">share</i>
      </div>
    </div>
    <div class="Card-description">
      <h3>{username}</h3>
      <span>{postComment}</span>
    </div>
    <Comments {comments} />
  </div>
</div>
