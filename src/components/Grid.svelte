<script lang="ts">
  import type { User } from "../types";
  import Card from "./Card.svelte";

  export let users: User[];
</script>

<h1 class="text-center text-3xl my-6">Grid View (Responsive)</h1>

<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 2xl:grid-cols-4 gap-4">
  {#each users as user}
    <Card {user} />
  {/each}
</div>
