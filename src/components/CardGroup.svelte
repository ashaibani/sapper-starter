<script>
  import MDBCardGroup from "mdbsvelte/src/MDBCardGroup.svelte";
  import MDBBtn from "mdbsvelte/src/MDBBtn.svelte";
  import MDBCard from "mdbsvelte/src/MDBCard.svelte";
  import MDBCardBody from "mdbsvelte/src/MDBCardBody.svelte";
  import MDBCardImage from "mdbsvelte/src/MDBCardImage.svelte";
  import MDBCardTitle from "mdbsvelte/src/MDBCardTitle.svelte";
  import MDBCardText from "mdbsvelte/src/MDBCardText.svelte";
  import MDBCol from "mdbsvelte/src/MDBCol.svelte";
</script>

<MDBCardGroup>
  <MDBCard>
    <MDBCardImage
      src="https://mdbootstrap.com/img/Photos/Others/images/49.jpg"
      alt="MDBCard image cap"
      top
      hover
      overlay="white-slight" />
    <MDBCardBody>
      <MDBCardTitle tag="h5">Panel title</MDBCardTitle>
      <MDBCardText>
        Some quick example text to build on the card title and make up the bulk
        of the card's content.
      </MDBCardText>
      <MDBBtn color="primary" size="md">read more</MDBBtn>
    </MDBCardBody>
  </MDBCard>

  <MDBCard>
    <MDBCardImage
      src="https://mdbootstrap.com/img/Photos/Others/images/48.jpg"
      alt="MDBCard image cap"
      top
      hover
      overlay="white-slight" />
    <MDBCardBody>
      <MDBCardTitle tag="h5">Panel title</MDBCardTitle>
      <MDBCardText>
        Some quick example text to build on the card title and make up the bulk
        of the card's content.
      </MDBCardText>
      <MDBBtn color="primary" size="md">read more</MDBBtn>
    </MDBCardBody>
  </MDBCard>

  <MDBCard>
    <MDBCardImage
      src="https://mdbootstrap.com/img/Photos/Others/images/77.jpg"
      alt="MDBCard image cap"
      top
      hover
      overlay="white-slight" />
    <MDBCardBody>
      <MDBCardTitle tag="h5">Panel title</MDBCardTitle>
      <MDBCardText>
        Some quick example text to build on the card title and make up the bulk
        of the card's content.
      </MDBCardText>
      <MDBBtn color="primary" size="md">read more</MDBBtn>
    </MDBCardBody>
  </MDBCard>
</MDBCardGroup>
