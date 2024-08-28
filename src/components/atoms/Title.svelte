<script lang="ts">
  export let text: string;
</script>

<h2>
  {text}
</h2>

<style lang="scss">
  @use '../../styles/colors.scss' as *;

  h2 {
    font-weight: 600;
    font-size: 22px;
    color: $primary;
  }
</style>
