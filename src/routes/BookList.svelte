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
  import { onMount } from 'svelte';

  let bookmarks = [];

  onMount(() => {
    
    const savedBookmarks = localStorage.getItem('bookmarks');
    if (savedBookmarks) {
      bookmarks = JSON.parse(savedBookmarks);
    }
  });
</script>

<main>
  <h1>Book List</h1>
  
  {#if bookmarks.length > 0}
    <ul>
      {#each bookmarks as bookmark}
        <li class="bookmark">
          <h2>{bookmark.title}</h2>
          <p>Author: {bookmark.author}</p>
        </li>
      {/each}
    </ul>
  {:else}
    <p>No bookmarks available.</p>
  {/if}
</main>



