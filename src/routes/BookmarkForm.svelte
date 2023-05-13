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
  import { createEventDispatcher, onMount, afterUpdate } from 'svelte';

  const dispatch = createEventDispatcher();
  let userInput = '';
  let authorInput = '';
  let bookmarks = [];

  function handleSubmit() {
    bookmarks.push({ title: userInput, author: authorInput });
    dispatch('bookmarks', bookmarks);
    userInput = '';
    authorInput = '';
    localStorage.setItem('bookmarks', JSON.stringify(bookmarks));
  }

  afterUpdate(() => {
    bookmarks = [...bookmarks];
  });

  onMount(() => {
    const savedBookmarks = localStorage.getItem('bookmarks');
    if (savedBookmarks) {
      bookmarks = JSON.parse(savedBookmarks);
    }
  });
</script>

<main>
<h1>Bookmarks</h1>
  <form on:submit|preventDefault={handleSubmit}>
    <label for="title-input" class="bookmark-form-label">Title:</label>
    <input type="text" id="title-input" bind:value={userInput} class="bookmark-form-input" />

    <label for="author-input" class="bookmark-form-label">Author:</label>
    <input type="text" id="author-input" bind:value={authorInput} class="bookmark-form-input" />

    <button type="submit" class="button">Add</button>
  </form>

  {#if bookmarks.length > 0}
    <h2 class="bookmark-list-heading">Book List:</h2>
    <ul class="bookmark-list">
      {#each bookmarks as bookmark}
        <li class="bookmark-item">
          <p class="bookmark-title">Title: {bookmark.title}</p>
          <p class="bookmark-author">Author: {bookmark.author}</p>
        </li>
      {/each}
    </ul>
  {:else}
    <p class="no-bookmarks">No bookmarks available.</p>
  {/if}
</main>




