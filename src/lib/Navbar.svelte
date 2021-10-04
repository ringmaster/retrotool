<nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <!-- svelte-ignore a11y-missing-attribute -->
        <img src="/retrotool.png" width="112" height="28">
      </a>
  
      <!-- svelte-ignore a11y-missing-attribute -->
      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>
  
    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <!-- svelte-ignore a11y-missing-attribute -->
        <a class="navbar-item">
          Home
        </a>
  
        <!-- svelte-ignore a11y-missing-attribute -->
        <a class="navbar-item">
          Documentation
        </a>
  
        <div class="navbar-item has-dropdown is-hoverable">
          <!-- svelte-ignore a11y-missing-attribute -->
          <a class="navbar-link">
            More
          </a>
  
          <!-- svelte-ignore a11y-missing-attribute -->
          <div class="navbar-dropdown">
            <!-- svelte-ignore a11y-missing-attribute -->
            <a class="navbar-item">
              About
            </a>
            <!-- svelte-ignore a11y-missing-attribute -->
            <a class="navbar-item">
              Jobs
            </a>
            <!-- svelte-ignore a11y-missing-attribute -->
            <a class="navbar-item">
              Contact
            </a>
            <hr class="navbar-divider">
            <a class="navbar-item">
              Report an issue
            </a>
          </div>
        </div>
      </div>
  
      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <!-- svelte-ignore a11y-missing-attribute -->
            <a class="button is-primary">
              <strong>Sign up</strong>
            </a>
            <!-- svelte-ignore a11y-missing-attribute -->
            <a class="button is-light">
              Log in
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>