<script>

  const states = ["landing-page", "sign-up-form", "user-info", "qr-code", "meet-driver","meet-premium-driver"];
 
 
 let pointer = 0
 
 function nextPage() {
    pointer += 1;
  }

  

  $: currentState = states[pointer];

  

  const services = [
    {name: "Karwa taxi", time: 400, price: 20, premium: true},
    {name: "Karwa bus", time: 800, price: 5, premium: true},
    {name: "Uber", time:410, price:35, premium: false},
    {name: "Careem", time:415, price:38, premium: false}

  ]

  let selected = services[0]
  

  //premium services bypass traffic
  

  let destination = "";

  let flightNumber = 0

  function chooseService() {
    if (selected.premium == true){
      swal("Booking Successful", "Meet with your driver at gate 4", "success");
      pointer = 5;
    }
    else {
      nextPage();
    }
  }

  function confirmBooking() {
    console.log("dfji")
    if (flightNumber.length == 6){
      swal("Booking Successful", "Head to the nearest checkpoint and show the qr code to meet with your driver", "success");
      nextPage();
    }
    else{
      swal("Invalid Pin", "Please Try Again", "error");
    }
  }
   
  let countDown = 123
  
  const format = seconds => new Date(seconds * 1000).toISOString().substr(11, 8);


  let warning = true




</script>


<style>
  .container{
    max-width: 680px; 
    margin: 0 auto;
    padding-top: 5vh
  }
</style>

<section class="container">
  
  {#if warning == true && selected.premium == false}
     <!-- content here -->
    <div class="notification is-danger">
      <button class="delete"></button>
      This service requires your to wait for your ride.
    </div>

  {/if}

  <div class="box">
  {#if currentState == "landing-page"}
    <section>
      <h1 class="title">Reach Your Final Destination Quickly</h1>
      <h4 class="subtitle">HIA partnered with Qatar's best transport services to get you home quickly and safely</h4>
    </section>
    <button class="button is-link" on:click={nextPage} >Book a Transport Service</button>

    {:else if  currentState == "sign-up-form"}
       <!-- else if content here -->
       <form on:submit|preventDefault={chooseService}>
          <div>
            <label class="label" >Destination</label>
            <input class="input" type="text" placeholder="Text input" bind:value = {destination}>
            
          </div>
          <br>
          <div>
            <!--{#if destination}-->
              <!-- content here -->
              <label class="label" >Service</label>

              <div class="select">
                <select bind:value={selected}>
                  {#each services as service}
                    <option value={service}>
                      {service.name} 
                    </option>
                  {/each}
                </select>
              </div>

              <!--
              <br>
              <div>
                speed:  { format(selected.time)  }
              </div>
              <div class="label">
                premium
                {#if selected.premium == true}
                  <i class="fas fa-check"></i>
                {:else}
                  <i class="fas fa-times"></i>
                {/if}
              </div>
              -->
              <br>
              <br>
              <div>
                <button class="button is-link" type=submit>
                  Submit
                </button>
              </div>
             
              
            <!--{/if}-->
          </div>  
        </form>

    {:else if  currentState == "user-info" }
       <!-- else if content here -->
       <div>
         <h1 class="subtitle">Enter your 6 digit Flight number to confirm trip to {destination}</h1>
       </div>
        <form on:submit|preventDefault={confirmBooking}>
          <input class="input" type="text" bind:value= {flightNumber}>
          <br>
          <br>
          <button class="button is-link" type=submit>
            Confirm
          </button>
        </form>

    {:else if  currentState == "qr-code"}
       <!-- else if content here -->
       <h1 class="subtitle"> Show this to the nearest checkpoint to meet with your driver</h1>

       <img src="./images/qr-code.png" alt="qr-code" on:click={nextPage}>

    {:else if  currentState == "meet-driver"}
        <!-- else if content here -->
      
      <div>
        <h4 class="subtitle">Driver Name: Jeremy Clarkson </h4>
      </div>
      <br>
      <div >
        <h4 class="subtitle">License Plate: j3zza </h4>
      </div>
      <br>
      <div >
        <h4 class="subtitle">Arriving in: {format(countDown)} </h4>
      </div>
      <br>

    {:else if  currentState == "meet-premium-driver"}
      
      <div>
        <h4 class="subtitle"> Your Driver is Waiting For You At Gate 4</h4>
      </div>
      <br>
      <a href="#fixed-tab-2" class="button is-link">Directions</a>
  {/if}
  
  </div>
  

</section>