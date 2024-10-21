<script>
    import { SignedIn, SignedOut, Doc, Collection } from 'sveltefire';
    import { signInWithEmailAndPassword } from "firebase/auth";
  </script>
  
  <SignedIn let:user let:signOut>
      <p>Hello {user.uid}</p>
      <button on:click={signOut}>Sign Out</button>
  </SignedIn>
  
  <SignedOut let:auth>
      <button on:click={() => signInWithEmailAndPassword(auth, "test@test.com", "test12")}>Sign In</button>
  </SignedOut>
  
  <Doc ref="posts/id" let:data>
      <h2>{data.title}</h2>
      <p>{data.content}</p>
  </Doc>
  
  <Collection ref="posts" let:data={posts}>
      {#each posts as post}
          <h2>{post.title}</h2>
          <p>{post.content}</p>
      {/each}
  </Collection>