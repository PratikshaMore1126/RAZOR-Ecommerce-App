<script>
  //Pages
  import Login from "./pages/Login.svelte";
  import About from "./pages/About.svelte";
  import Home from "./pages/Home.svelte";
  import Checkout from "./pages/Checkout.svelte";
  import Products from "./pages/Products.svelte";
  import ProductTemplate from "./pages/ProductTemplate.svelte";

  //router
  import { Router, Route, Link } from "svelte-routing";
  // components
  import Navbar from "./components/Navbar/Navbar.svelte";
  import Sidebar from "./components/Navbar/Sidebar.svelte";
  import Cart from "./components/Cart/Cart.svelte";
  // global store
  import globalStore from "./stores/globalStore";
</script>

<Router>
  <Navbar />
  <!-- sidebar -->
  {#if $globalStore.sidebar}
    <Sidebar />
  {/if}
  <!-- cart -->
  {#if $globalStore.cart}
  <Cart />
  {/if}


  <Route path="/" component={Home}></Route>
  <Route path="/about" component={About}></Route>
  <Route path="/products" component={Products}></Route>
  <Route path="/products/:id" component={ProductTemplate}></Route>
  <Route path="/login" component={Login}></Route>
</Router>
