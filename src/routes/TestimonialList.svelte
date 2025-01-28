<script lang="ts">
  import Marquee from "svelte-fast-marquee";

  interface Props {
    data: {
      name: string;
      role: string;
      quote: string;
      link?: string;
    }[];
  }

  let { data }: Props = $props();
</script>

<Marquee gap="1rem" pauseOnHover={true}>
  {#each data as t, idx}
    <blockquote
      class="relative my-0 flex h-full w-[83cqw] flex-none flex-col rounded bg-neutral-100 dark:bg-neutral-800"
    >
      <!-- svelte-ignore a11y_missing_content -->
      {#if t.link}
        <a
          href={t.link}
          target="_blank"
          class="absolute inset-0 rounded rounded-l-none border border-transparent transition hover:border-neutral-200 dark:hover:border-neutral-700"
          aria-label="View Testimonial"
        ></a>
      {/if}

      <p>{@html t.quote}</p>
      <span class="mt-auto ml-auto p-4 pt-0 text-end">
        ~ {t.name}, {t.role}
      </span>
    </blockquote>
  {/each}
</Marquee>
