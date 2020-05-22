<script>
  import MDBContainer from "mdbsvelte/src/MDBContainer.svelte";
  import MDBRow from "mdbsvelte/src/MDBRow.svelte";
  import MDBCol from "mdbsvelte/src/MDBCol.svelte";
  import MDBIcon from "mdbsvelte/src/MDBIcon.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";
  import MDBCardTitle from "mdbsvelte/src/MDBCard.svelte";
  import MDBJumbotron from "mdbsvelte/src/MDBCardBody.svelte";
</script>

<section id="hero">
  <MDBContainer>
    <MDBRow>
      <MDBCol>
        <MDBJumbotron style="padding: 0">
          <MDBCol
            class="text-white text-center py-5 px-4 my-5"
            style="background-image:
            url(https://mdbootstrap.com/img/Photos/Others/gradient1.jpg)">
            <MDBCol class="py-5">
              <h1>Hero Title</h1>
              <p class="mx-5 mb-5">
                Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                Repellat fugiat, laboriosam, voluptatem, optio vero odio nam sit
                officia accusamus minus error nisi architecto nulla ipsum
                dignissimos. Odit sed qui, dolorum!
              </p>
              <MDBBtn outline color="white" class="mb-5">
                <MDBIcon icon="clone" class="mr-2" />
                GOTO SOMEWHERE
              </MDBBtn>
            </MDBCol>
          </MDBCol>
        </MDBJumbotron>
      </MDBCol>
    </MDBRow>
  </MDBContainer>

</section>
