<script>
  // cart button
  import CartButton from "../Cart/CartButton.svelte";
  //  global store
  import { link } from "svelte-routing";
  import globalStore from "../../stores/globalStore";
  let openSidebar = globalStore.toggleItem;
</script>

<nav class="navbar">
  <div class="nav-center">
    <!-- sidebar toggle -->
    <button
      class="btn-sidebar-toggle"
      on:click={() => {
        openSidebar("sidebar", true);
      }}
    >
      <i class="fas fa-bars" />
    </button>
    <!-- logo -->
    <a href="/" use:link class="nav-logo">
      <!-- <img src="/asserts/images/logo.svg" class="logo" alt="razors logo" /> -->
      <h1>razors</h1>
    </a>
    <!-- cart button -->
    <CartButton />
  </div>
</nav>
