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
  
  let email = '';
  let password = '';

  function handleLogin() {
    
    console.log('Logging in...');
    console.log('Email:', email);
    console.log('Password:', password);
    
  }
</script>

<main>
  <h1>Login</h1>
  <form on:submit|preventDefault={handleLogin} class="login-form">
    <label for="email">Email</label>
    <input type="email" id="email" bind:value={email} />

    <label for="password">Password</label>
    <input type="password" id="password" bind:value={password} />

    <button type="submit" class="login-button">Login</button>
  </form>
</main>


