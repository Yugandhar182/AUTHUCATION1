
<script>
   import { goto } from '$app/navigation';
  import Profile from "$lib/profile/profile.svelte"
  
  
  
  
  // Function to handle logout
  function handleLogout() {
    // Display a confirmation dialog
    const confirmLogout = window.confirm("Are you sure you want to logout?");
    
    if (confirmLogout) {
      // User confirmed, proceed with logout
      // You can use your Firebase auth instance to sign the user out
      // For example:
      auth.signOut().then(() => {
        // Handle successful logout, e.g., navigate to the /information page
        console.log("User logged out");
        goto('/'); // Navigate to the /information route
      }).catch((error) => {
        // Handle logout error, if any
        console.error("Logout error:", error);
      });
    }
  }

  function candidatelist() {
    goto('/candidatelist');
   
  }
  function joblist() {
    goto('/joblist');
   
  }

  

</script>
<main>

<div class="flex-container">
    <div class="item-1"></div>
    <div class="item-2">
        <div class="mb-6">
            <i class="fa fa-mortar-board" on:click={candidatelist} style="font-size: 26px; color: white; margin-top: 45px;">Candidates</i>
              </div>
              <div class="mb-6">
            <i class="fa fa-briefcase"   on:click={joblist} style="font-size: 26px; color: white; margin-top: 30px; margin-left:-70px" >Jobs</i>
              </div>
    </div>
  </div>
</main>
<div class="container2">
    <Profile/>
    </div>


  <style>
    .flex-container {
      display: flex;
      flex-direction: column;
      background-color:white;
      height: 100vh; /* Set height to 100% viewport height */
      margin-top: -720px;
      width: 100%;
    }
  
    .item-1 {
      background-color:rgb(45, 36, 220);
      width: 100%; /* Set width to 50% of the container */
      margin: 0px;
      text-align: center;
      line-height: 75px;
      font-size: 30px;
      height:15%; /* Allow the height to adjust based on content */
      /* Additional styles for item-1 */
    }
  
    .item-2 {
        background-color:rgb(45, 36, 220);
      width: 13%; /* Set width to 50% of the container */
      margin: 00px;
      text-align: center;
      font-size: 30px;
      height:100%; /* Allow the height to adjust based on content */
      /* Additional styles for item-2 */
      max-width: 100%;
    }
  
    @media screen and (max-width: 768px) {
      /* Media query for screens with a maximum width of 768px */
      .item-1,
      .item-2 {
        width: 100%; /* Set width to 100% on smaller screens */
        margin: 5px; /* Adjust margin as needed */
      }
    }
  </style>
  