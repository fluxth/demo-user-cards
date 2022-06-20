<script lang="ts">
  import type { User } from "../types";
  import ThreeBars from "./icons/ThreeBars.svelte";
  import Question from "./icons/Question.svelte";

  export let user: User;
</script>

<div class="p-6 border border-violet-200 rounded-2xl font-mono">
  <div class="mb-12 text-center">
    <div
      class="mb-6 w-60 h-60 mx-auto bg-violet-300 rounded-3xl flex justify-center items-center
    text-2xl text-white"
    >
      Picture
    </div>
    <div class="mx-2 text-center text-sm font-semibold">
      {user.name} #{user.id}
    </div>
  </div>

  <div class="flex flex-col gap-2 text-sm font-light">
    <div class="flex justify-between items-center">
      <div class="text-neutral-500 flex gap-1">Estimated Price <Question /></div>
      <div class:text-neutral-500={user.estPrice === 0}>
        <ThreeBars />{user.estPrice.toFixed(3)}
      </div>
    </div>
    <div class="flex justify-between">
      <div class="text-neutral-500">Floor Price <Question /></div>
      <div class:text-neutral-500={user.floorPrice === 0}>
        <ThreeBars />{user.floorPrice.toFixed(3)}
      </div>
    </div>
    <div class="flex justify-between">
      <div class="text-neutral-500">Acquisition Price <Question /></div>
      <div class:text-neutral-500={user.acqPrice === 0}>
        <ThreeBars />{user.acqPrice.toFixed(3)}
      </div>
    </div>
    <div class="flex justify-between">
      <div class="text-neutral-500">Acquisition Date</div>
      <div>
        {user.acqDate}
      </div>
    </div>
  </div>
</div>
