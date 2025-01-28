<script lang="ts">
  interface Props {
    text?: string;
    href?: string;
  }

  let { text = "", href = "" }: Props = $props();
</script>

<a {href} target="_blank">{text}</a>
