<script>
  import { createEventDispatcher } from "svelte";

  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import MDBRow from "mdbsvelte/src/MDBRow.svelte";
  import MDBCol from "mdbsvelte/src/MDBCol.svelte";
  import MDBInput from "mdbsvelte/src/MDBInput.svelte";
  import MDBIcon from "mdbsvelte/src/MDBIcon.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";
  import MDBCard from "mdbsvelte/src/MDBCard.svelte";
  import MDBCardBody from "mdbsvelte/src/MDBCardBody.svelte";

  const dispatch = createEventDispatcher();

  let username;
  let password;

  async function sendLogin() {
    dispatch("login", {
      username: username,
      password: password
    });
  }
</script>

<MDBContainer>
  <MDBRow>
    <MDBCol md="6" class="offset-md-3">
      <MDBCard>
        <div class="header pt-3 blue-gradient">
          <MDBRow class="d-flex justify-content-center">
            <h3 class="white-text mb-3 pt-3 font-weight-bold">LOG IN</h3>
            <br />
          </MDBRow>
        </div>
        <MDBCardBody class="mx-4 mt-4">
          <MDBInput
            label="YOUR EMAIL"
            group
            type="text"
            bind:value={username}
            validate />
          <MDBInput
            label="YOUR PASSWORD"
            group
            type="password"
            bind:value={password}
            validate
            containerClass="mb-0" />
          <p class="font-small grey-text d-flex justify-content-end">
            Forgot
            <a href="reset" class="dark-grey-text ml-1 font-weight-bold">
              Password?
            </a>
          </p>
          <MDBRow class="d-flex align-items-center mb-4 mt-5">
            <MDBCol md="5" class="d-flex align-items-start">
              <div class="text-center">
                <MDBBtn
                  color="black"
                  rounded
                  type="button"
                  class="z-depth-1a"
                  on:click={sendLogin}>
                  Log in
                </MDBBtn>
              </div>
            </MDBCol>
            <MDBCol md="7" class="d-flex justify-content-end">
              <p class="font-small black-text mt-3">
                Don't have an account?
                <a href="signup" class="black-text ml-1 font-weight-bold">
                  Sign up
                </a>
              </p>
            </MDBCol>
          </MDBRow>
        </MDBCardBody>
      </MDBCard>
    </MDBCol>
  </MDBRow>
</MDBContainer>
