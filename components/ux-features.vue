<template>
  <ul>
    <card
      icon="⌨️"
      heading="Ticket History"
      subheading="Know your customers most pressing and time sensitive issues."
      bg="https://res.cloudinary.com/da32ufmnf/image/upload/v1645805170/atlas/f8kyzjyzmdpcftqd0bmc.png"
    />

    <card
      icon="🧰"
      heading="Command menu"
      subheading="Know your customers most pressing and time sensitive issues."
      bg="https://res.cloudinary.com/da32ufmnf/image/upload/v1645805170/atlas/f8kyzjyzmdpcftqd0bmc.png"
    />

    <card
      icon="🔎️"
      heading="Search"
      subheading="Know your customers most pressing and time sensitive issues."
      bg="https://res.cloudinary.com/da32ufmnf/image/upload/v1645805170/atlas/f8kyzjyzmdpcftqd0bmc.png"
    />
  </ul>
</template>

<style lang="scss" scoped>
  @import "~static/style/grid.scss";

  ul {
    display: grid;
    grid-column-gap: 56px;
    grid-row-gap: 24px;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  }

  li {
    padding: 1.2rem 1.6rem;
    @include breakpoint(md) {
      padding: 1.6rem 2rem;
      /* width: grid-width(3.8); */
    }
  }
</style>

<script>
  export default {}
</script>
