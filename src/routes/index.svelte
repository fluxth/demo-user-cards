<script lang="ts">
  import "../app.css";
  import type { User } from "../types";

  import Button from "../components/Button.svelte";
  import Grid from "../components/Grid.svelte";
  import List from "../components/List.svelte";

  let isGrid = true;
  let users: User[] = new Array(8)
    .fill([
      {
        id: 420,
        name: "LinuxPenguin",
        estPrice: 5.19,
        floorPrice: 5.19,
        acqPrice: 5.19,
        acqDate: "Jun 9, 2022",
      },
      {
        id: 69,
        name: "MissA",
        estPrice: 0,
        floorPrice: 1.88,
        acqPrice: 0.69,
        acqDate: "Jan 12, 1988",
      },
      {
        id: 112,
        name: "MisterX",
        estPrice: 1.555,
        floorPrice: 0,
        acqPrice: 2.001,
        acqDate: "Dec 5, 1944",
      },
    ])
    .flat();
</script>

<div class="container mx-auto px-4 py-6">
  <div class="text-center">
    <Button {isGrid} on:click={() => (isGrid = !isGrid)} />
  </div>

  <div class="mt-4">
    {#if isGrid}
      <Grid {users} />
    {:else}
      <List {users} />
    {/if}
  </div>
</div>
