<script>
  import MDBNav from "mdbsvelte/src/MDBNav.svelte";
  import MDBNavLink from "mdbsvelte/src/MDBNavLink.svelte";
  import MDBNavbar from "mdbsvelte/src/MDBNavbar.svelte";
  import MDBNavbarBrand from "mdbsvelte/src/MDBNavbarBrand.svelte";
  import MDBNavbarToggler from "mdbsvelte/src/MDBNavbarToggler.svelte";
  import MDBNavbarNav from "mdbsvelte/src/MDBNavbarNav.svelte";
  import MDBNavItem from "mdbsvelte/src/MDBNavItem.svelte";
  import MDBCollapse from "mdbsvelte/src/MDBCollapse.svelte";
  import MDBDropdownMenu from "mdbsvelte/src/MDBDropdownMenu.svelte";
  import MDBDropdownItem from "mdbsvelte/src/MDBDropdownItem.svelte";
  import MDBDropdownToggle from "mdbsvelte/src/MDBDropdownToggle.svelte";
  import MDBDropdown from "mdbsvelte/src/MDBDropdown.svelte";
  import MDBFormInline from "mdbsvelte/src/MDBFormInline.svelte";

  export var currentUser;
  let isOpen = false;

  function toggleCollapse() {
    isOpen = !isOpen;
  }

  function handleUpdate(event) {
    isOpen = event.detail.isOpen;
  }
</script>

<MDBNavbar color="blue-gradient" dark expand="md">
  <MDBNavbarBrand>
    <strong class="white-text">Navbar</strong>
  </MDBNavbarBrand>
  <MDBNavbarToggler on:click={toggleCollapse} />
  <MDBCollapse
    id="navbarCollapse3"
    {isOpen}
    navbar
    expand="md"
    on:update={handleUpdate}>
    <MDBNavbarNav left>
      <MDBNavItem>
        <MDBNavLink href="/">HOME</MDBNavLink>
      </MDBNavItem>
      {#if currentUser}
        <MDBNavItem>
          <MDBDropdown>
            <MDBDropdownToggle nav caret>
              <span class="mr-2">DROPDOWN</span>
            </MDBDropdownToggle>
            <MDBDropdownMenu>
              <MDBDropdownItem href="#!">ACTION</MDBDropdownItem>
              <MDBDropdownItem href="#!">ANOTHER ACTION</MDBDropdownItem>
              <MDBDropdownItem href="#!">SOMETHING ELSE HERE</MDBDropdownItem>
            </MDBDropdownMenu>
          </MDBDropdown>
        </MDBNavItem>
      {:else}
        <MDBNavItem>
          <MDBNavLink href="login">LOGIN</MDBNavLink>
        </MDBNavItem>
        <MDBNavItem>
          <MDBNavLink href="signup">SIGNUP</MDBNavLink>
        </MDBNavItem>
      {/if}

    </MDBNavbarNav>
    <MDBNavbarNav right>
      {#if currentUser}
        <MDBNavItem>
          <MDBNavLink href="logout">LOGOUT</MDBNavLink>
        </MDBNavItem>
      {/if}

      <MDBNavItem>
        <MDBFormInline waves>
          <div class="md-form my-0">
            <input
              class="form-control mr-sm-2"
              type="text"
              placeholder="SEARCH"
              aria-label="SEARCH" />
          </div>
        </MDBFormInline>
      </MDBNavItem>
    </MDBNavbarNav>
  </MDBCollapse>
</MDBNavbar>
