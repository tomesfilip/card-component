<script lang="ts">
  export let text: string;
</script>

<button type="button">
  {text}
</button>

<style lang="scss">
  @use '../../styles/colors.scss' as *;

  button {
    font-weight: 700;
    font-size: 16px;
    padding: 14px 24px;
    border-radius: 0 8px 8px 8px;
    background: transparent;
    border: 2px solid $primary;
    color: $primary;
    cursor: pointer;
    transition: all 0.2s ease-out;

    &:hover {
      background: $primary;
      color: white;
    }
  }
</style>
