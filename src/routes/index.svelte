<script lang="ts">
  import {formatDistanceToNowStrict, format} from "date-fns";

  export let ow2ReleaseDate = new Date(2077, 4, 20);
  $: isOW2Out = new Date(Date.now()) > ow2ReleaseDate;
  let releaseDateAnnounced = false;
</script>

<div class="flex flex-col justify-center items-center h-[100vh] w-[100vw]">
  <div class="flex-grow flex flex-col justify-center items-center py-8">
    <h1 class="text-6xl font-display font-medium dark:text-slate-100">{isOW2Out ? "Yes." : "No."}</h1>
    <p class="my-4 italic dark:text-slate-100">{releaseDateAnnounced ? `${formatDistanceToNowStrict(ow2ReleaseDate)} until release on ${format(ow2ReleaseDate, "MMMM do, yyyy")}` : "...and no release date has been announced yet."}</p>
  </div>
  <div class="flex justify-between my-4 mx-2 px-4 h-8 w-full">
    <p class="text-xs text-gray-500 dark:text-slate-400 italic text-left">Created by <a class="text-blue-600 dark:text-blue-300 underline" href="https://twitter.com/Cactus_Puppy" rel="noreferrer noopener" target="_blank">@Cactus_Puppy</a><br /><a href="https://github.com/CactusPuppy/isow2outyet" rel="noreferrer noopener" target="_blank" class="text-blue-600 dark:text-blue-300 underline">GitHub</a></p>
    <p class="text-xs text-gray-500 dark:text-slate-400 italic text-right">
      This site and its creator are not affiliated with Overwatch or Blizzard Entertainment.
      <br />Overwatch 2 and the Overwatch 2 logo are ©2022 Blizzard Entertainment, Inc.
    </p>
  </div>
</div>
