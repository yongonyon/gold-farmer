<script>
  export let segment;
</script>

<nav class="navbar navbar-expand-lg sticky-top navbar-dark bg-dark">
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarTogglerDemo03"
    aria-controls="navbarTogglerDemo03"
    aria-expanded="false"
    aria-label="Toggle navigation">
    <span class="navbar-toggler-icon" />
  </button>
  <a class="navbar-brand" href=".">Gold Farmer</a>

  <div class="collapse navbar-collapse" id="navbarTogglerDemo03">
    <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
      <li class="nav-item active">
        <a class="nav-link" class:selected={segment === undefined} href="/shop">
          Shop
          <span class="sr-only">(current)</span>
        </a>
      </li>
    </ul>
  </div>
</nav>
