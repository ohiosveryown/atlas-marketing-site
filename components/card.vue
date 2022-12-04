<template>
  <li class="wrapper">
    <header>
      <i>{{ icon }}</i>
      <h3 class="inter">
        {{ heading }}
      </h3>
    </header>
    <p>
      {{ subheading }}
    </p>
  </li>
</template>

<style lang="scss" scoped>
  @import "~static/style/grid.scss";

  li {
    position: relative;
    border-radius: 20px;
    background: linear-gradient(
      135deg,
      rgba(58, 51, 73, 0.8) 2%,
      rgba(58, 51, 73, 0.22) 88%
    );
    box-shadow: 0px 100px 80px rgba(0, 0, 0, 0.75),
      0px 12px 10px rgba(0, 0, 0, 0.375), inset 0px 1px 1px #5c546c;
    overflow: hidden;
  }

  i {
    position: relative;
    z-index: var(--z2);
    font-size: 3rem;
    font-style: normal;
  }

  h3 {
    position: relative;
    z-index: var(--z2);
    margin: 0.4rem 0 1rem;
    text-transform: capitalize;

    @include breakpoint(md) {
      font-size: 2rem;
    }
  }

  p {
    position: relative;
    z-index: var(--z2);
    margin-bottom: 2rem;
    font-size: 1.8rem;
    color: #c7c3cd;
  }

  .product {
    position: relative;
    z-index: var(--z2);
  }
</style>

<script>
  export default {
    props: ["icon", "heading", "subheading", "product", "bg"],
  }
</script>
