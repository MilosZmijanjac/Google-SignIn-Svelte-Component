<head>
  <script src="https://accounts.google.com/gsi/client" async defer></script>
</head>

<script>
  export let clientId,jwtoken;
  function handleCredentialResponse(response) {
    jwtoken=response.credential
  }
  window.onload = function () {
    google.accounts.id.initialize({
      client_id: clientId,
      callback: handleCredentialResponse
    });
    google.accounts.id.renderButton(
      document.getElementById("buttonDiv"),
      { theme: "outline", size: "large" }  // customization attributes
    );
    google.accounts.id.prompt(); // also display the One Tap dialog
  }
</script>
<div id="buttonDiv"></div> 
