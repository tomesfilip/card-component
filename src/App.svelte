<script lang="ts">
  import placeholderImg from './assets/img/placeholder.svg';
  import Card from './components/moleculs/Card.svelte';
</script>

<main>
  <Card
    title="Lorem ipsum"
    description="Lorem ipsum dolor sit amet.."
    buttonText="Lorem ipsum"
    imgSrc={placeholderImg}
    imgAlt="placeholder image"
    tooltip="Lorem"
    tooltipHover="Tooltip - lorem ipsum"
  />
</main>

<style lang="scss">
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2rem;
  }
</style>
