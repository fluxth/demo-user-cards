<script lang="ts">
  import type { User } from "../types";
  import ThreeBars from "./icons/ThreeBars.svelte";
  import Question from "./icons/Question.svelte";

  export let users: User[];
</script>

<h1 class="text-center text-3xl my-6">List View</h1>

<div class="flex flex-col">
  <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
    <div class="py-2 inline-block min-w-full sm:px-6 lg:px-8">
      <div class="overflow-hidden">
        <table class="min-w-full table-auto">
          <thead class="border-b">
            <tr>
              <th scope="col" />
              <th scope="col" class="text-sm font-medium text-gray-900 px-4 py-2 text-center">
                User
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-4 py-2 text-left">
                Est. Price
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-4 py-2 text-left">
                Floor Price
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-4 py-2 text-left">
                Acq. Price
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-4 py-2 text-right">
                Acq. Date
              </th>
              <th />
            </tr>
          </thead>
          <tbody>
            {#each users as user}
              <tr class="bg-white font-mono">
                <td class="px-4 py-2 whitespace-nowrap text-sm w-4">
                  <div
                    class="bg-black w-10 h-10 rounded-xl text-white flex justify-center items-center"
                  >
                    :)
                  </div>
                </td>
                <td class="text-sm px-4 py-2 whitespace-nowrap">
                  <div class="flex items-center gap-3">
                    <div
                      class="bg-violet-400 w-10 h-10 rounded-xl text-white flex justify-center items-center"
                    >
                      P
                    </div>
                    {user.name} #{user.id}
                  </div>
                </td>
                <td
                  class="text-sm px-4 py-2 whitespace-nowrap"
                  class:text-neutral-500={user.estPrice === 0}
                >
                  <ThreeBars />{user.estPrice.toFixed(3)}
                  <Question />
                </td>
                <td
                  class="text-sm px-4 py-2 whitespace-nowrap"
                  class:text-neutral-500={user.floorPrice === 0}
                >
                  <ThreeBars />{user.floorPrice.toFixed(3)}
                  <Question />
                </td>
                <td
                  class="text-sm px-4 py-2 whitespace-nowrap"
                  class:text-neutral-500={user.acqPrice === 0}
                >
                  <ThreeBars />{user.acqPrice.toFixed(3)}
                  <Question />
                </td>
                <td class="text-sm px-4 py-2 whitespace-nowrap text-right text-neutral-500">
                  {user.acqDate}
                </td>
                <td class="px-4 py-2 whitespace-nowrap text-sm font-medium w-1">
                  <button
                    class="bg-white hover:bg-neutral-100 border w-8 h-8 rounded-lg text-black flex justify-center items-center"
                  >
                    E
                  </button>
                </td>
              </tr>
            {/each}
          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>
