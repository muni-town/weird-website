<script>
  import Content from "../components/Content.svelte";
  import rawMarkdown from "./magic-website-creator.md?raw";

  const heading = "Magic website creator";
  const description =
    "To fully inhabit the World Wide Web (interwebs for fun, or just the web for short), you need to create your digital self within it.";
</script>

<Content {heading} {rawMarkdown} {description} />
