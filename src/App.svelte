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
  import { Router, Route } from 'svelte-routing';
  import Home from './routes/Home.svelte';  
  import BookList from './routes/BookList.svelte';
  import BookmarkForm from './routes/BookmarkForm.svelte'; 
  import Details from './routes/Details.svelte';
  import Signup from './routes/Signup.svelte';
  import Login from './routes/Login.svelte';
  import { navigate } from 'svelte-routing';  
  import Footer from './routes/Footer.svelte'; 

  
  let bookmarks = [];  

  function navigateToHome() {
    navigate('/');
  } 

  function navigateToBookList() {
    navigate('/books');
  }

  function navigateToBookmark() {
    navigate('/bookmark');
  }

  function handleBookmark(event) {
    const { title, url } = event.detail;
    bookmarks.push({ title, url }); 
  }  
</script>

<main>
<container class="container">
  <nav>
    <ul>
      <li>
        <a href="/" on:click|preventDefault={navigateToHome}>Home</a>
      </li>
      <li>
        <a href="/books" on:click|preventDefault={navigateToBookList}>Book List</a>
      </li>
      <li>
        <a href="/bookmark" on:click|preventDefault={navigateToBookmark}>Bookmarks</a> 
      </li>
      <li>
        <a href="/signup" on:click|preventDefault={navigateToSignup}>Sign Up</a>
      </li>
      <li>
        <a href="/login" on:click|preventDefault={navigateToLogin}>Login</a>
      </li>
    </ul>
  </nav>

  <Router>
    <Route path="/" component={Home} />    
    <Route path="/books" component={BookList} />
    <Route path="/bookmark" component={BookmarkForm} on:bookmark={handleBookmark} /> 
    <Route path="/details/:id" component={Details} />
    <Route path="/signup" component={Signup} />
    <Route path="/login" component={Login} />
  </Router>
  <Footer />
  </container>
</main>







