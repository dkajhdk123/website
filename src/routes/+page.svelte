<script lang="ts">
  import CaseSection from '$components/CaseSection.svelte';
  import type { CaseSection as CaseSectionType } from '$lib';

  export let data: { sections: CaseSectionType[] };
</script>

<main class="bg-no-repeat" style="background-position: center top; background-size: auto 1400px;">
  <div class="relative">
    <div id="caseList-root" class="py-10 pb-10">
      <div class="min-h-screen text-white">
        <div class="container mx-auto">
          <!-- {#await promise then data} -->
          {#each data.sections as sectionData}
            {#if sectionData.cases.length > 0}
              <CaseSection data="{sectionData}" />
            {/if}
          {/each}
          <!-- {/await} -->
        </div>
      </div>
    </div>
  </div>
</main>
