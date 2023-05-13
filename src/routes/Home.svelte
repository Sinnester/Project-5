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
  import { navigate } from 'svelte-routing';

  function navigateToBookmark() {
    navigate('/bookmark');
  }
</script>


<main>
  <section class="bookmark-page">
    <h1>Welcome to the Bookmark System</h1>
    <p>Organize your favorite books with bookmarks!</p>
    
  </section>

  <section class="features">
    <h2>Key Features:</h2>
    <ul>
      <li class="list-item">Create bookmarks for your favorite books</li>
      <li class="list-item">Save and manage your reading list</li>
      <li class="list-item">Easy access to book details</li>
      <li class="list-item">Personalize your book collection</li>
    </ul>
  </section>
</main>





