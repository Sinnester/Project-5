<!----------------------------------------------------------------------------------------------------------------
--
#Original Author: Derek Little                                       #
#Date Created: 5/12/2023                                         #
#Version: 0.0                                                  #
#Date Last Modified: 5/12/2023                                #
#Modified by: Derek Little                                           #
#Modification log: 
  V0.0~ Added everything. (5/12/2023)                                    #
 --
------------------------------------------------------------------------------------------------------------------>
<script>
  
  let username = '';
  let email = '';
  let password = '';

  function handleSignup() {
    
    console.log('Signing up...');
    console.log('Username:', username);
    console.log('Email:', email);
    console.log('Password:', password);
    
  }
</script>

<main>
  <h1>Sign Up</h1>
  <form on:submit|preventDefault={handleSignup} class="signup-form">
    <label for="email">Email</label>
    <input type="email" id="email" bind:value={email} />
    
    <label for="username">Username</label>
    <input type="text" id="username" bind:value={username} />    

    <label for="password">Password</label>
    <input type="password" id="password" bind:value={password} />
    <hr />

    <button type="submit" class="signup-button">Sign Up</button>
  </form>
</main>


