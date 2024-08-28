<script lang="ts">
  import Button from '../atoms/Button.svelte';
  import Title from '../atoms/Title.svelte';

  export let imgSrc: string;
  export let imgAlt: string;
  export let title: string;
  export let description: string;
  export let buttonText: string;
  export let tooltip: string;
  export let tooltipHover: string;
</script>

<div class="card">
  <div class="tooltip" aria-label={tooltipHover}>
    {tooltip}
    <span class="tooltiptext">{tooltipHover}</span>
  </div>
  <img class="image" src={imgSrc} alt={imgAlt} />
  <div class="content">
    <div class="text">
      <Title text={title} />
      <p>{description}</p>
    </div>
    <Button text={buttonText} />
  </div>
</div>

<style lang="scss">
  @use '../../styles/colors.scss' as *;

  .card {
    position: relative;
    border-radius: 0 24px 24px 24px;
    box-shadow: 0 5px 20px 0 rgba(0, 0, 0, 0.05);
    background-color: #fff;
    max-width: 320px;
    width: 100%;

    &::after {
      content: '';
      position: absolute;
      bottom: 0;
      right: 0;
      width: 100%;
      height: 100%;
      background: url('../../assets/img/card-bottom.svg') no-repeat bottom right;
      opacity: 0.3;
      pointer-events: none;
    }

    .image {
      width: 100%;
      max-width: 320px;
      height: 250px;
      object-fit: cover;
      border-radius: 0 24px 0 0;
    }

    .content {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 24px;
      row-gap: 28px;

      .text {
        text-align: center;
        display: flex;
        flex-direction: column;
        row-gap: 16px;
      }
    }

    .tooltip {
      font-weight: 600;
      color: white;
      padding: 2px 4px;
      border-radius: 4px;
      background-color: $primary;
      position: absolute;
      top: 8px;
      left: 8px;
      display: inline-block;
      font-size: 14px;
      z-index: 2;

      .tooltiptext {
        visibility: hidden;
        font-size: 12px;
        background-color: black;
        color: white;
        padding: 5px 6px;
        position: absolute;
        z-index: 1;
        bottom: 120%;
        left: -60%;
        border-radius: 4px;
        width: max-content;

        &::after {
          content: '';
          position: absolute;
          top: 100%;
          left: 50%;
          margin-left: -5px;
          border-width: 5px;
          border-style: solid;
          border-color: black transparent transparent transparent;
        }
      }

      &:hover .tooltiptext {
        visibility: visible;
      }
    }
  }
</style>
