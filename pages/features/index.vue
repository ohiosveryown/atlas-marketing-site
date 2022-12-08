<template>
  <div class="app">
    <HeaderMedium
      class="width page-header tac"
      heading="Features"
      subheading="A fully integrated suite of support products."
    />

    <main class="width">
      <section class="enter icon-wrapper">
        <ul class="icons">
          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/yoosdxzeshd8ljparxwc.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/i5zz7nglrnrfpss86ae8.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/kpremdyi4m1mgxftjm1f.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/yoosdxzeshd8ljparxwc.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/i5zz7nglrnrfpss86ae8.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/kpremdyi4m1mgxftjm1f.png"
              alt=""
              class="icon"
            />
          </li>
        </ul>

        <ul class="icons">
          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/yoosdxzeshd8ljparxwc.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/i5zz7nglrnrfpss86ae8.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/kpremdyi4m1mgxftjm1f.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/yoosdxzeshd8ljparxwc.png"
              alt=""
              class="icon"
            />
          </li>

          <li>
            <img
              src="https://res.cloudinary.com/da32ufmnf/image/upload/v1669129127/atlas-refresh/features/i5zz7nglrnrfpss86ae8.png"
              alt=""
              class="icon"
            />
          </li>
        </ul>
      </section>

      <section class="features">
        <h3 class="tac inter">All-in-one</h3>
        <ul class="feature-grid">
          <li class="card" v-for="feature of featuresss" :key="feature.slug">
            <img class="icon" :src="`${feature.icon}`" />
            <NuxtLink :to="'/features/' + feature.slug">
              <h4 class="inter">{{ feature.name }}</h4>
              <p class="dark">{{ feature.subheader }}</p>
            </NuxtLink>
            <img class="hero" :src="`${feature.hero}`" />
          </li>
        </ul>
      </section>

      <section class="features">
        <h3 class="tac inter">Customer Centric</h3>
        <ul class="feature-grid">
          <li class="card" v-for="feature of features" :key="feature.slug">
            <img class="icon" :src="`${feature.icon}`" />
            <NuxtLink :to="'/features/' + feature.slug">
              <h4 class="inter">{{ feature.name }}</h4>
              <p class="dark">{{ feature.subheader }}</p>
            </NuxtLink>
            <img class="hero" :src="`${feature.hero}`" />
          </li>
        </ul>
      </section>
    </main>
  </div>
</template>

<style lang="scss" scoped>
  @import "~static/style/grid.scss";

  .page-header {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 4rem auto 1.2rem;
    @include breakpoint(md) {
      margin: 8rem auto 4rem;
      width: grid-width(6);
    }
    @include breakpoint(lg) {
      width: grid-width(4.5);
    }
  }

  section.icon-wrapper {
    margin: 0 auto 4rem;
    @include breakpoint(md) {
      margin-bottom: 6.4rem;
      width: grid-width(6);
    }
  }
  ul.icons {
    display: flex;
    justify-content: center;
  }
  .icon {
    width: 88px;
  }
  section.features {
    margin-bottom: 4.8rem;
    @include breakpoint(md) {
      margin-bottom: 9.6rem;
    }
    header {
      margin-bottom: 2.4rem;
      text-align: center;
      @include breakpoint(mdl) {
        text-align: left;
        margin-bottom: 4.8rem;
        width: grid-width(6);
      }
    }
    .feature-grid {
      @include breakpoint(md) {
        display: grid;
        grid-column-gap: 28px;
        grid-row-gap: 28px;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
      }
    }
    .card {
      height: fit-content;
      position: relative;
      border-radius: 20px;
      margin-bottom: 4rem;
      padding: 2rem;
      background: linear-gradient(
        135deg,
        rgba(58, 51, 73, 1) 2%,
        rgba(58, 51, 73, 0.22) 88%
      );
      box-shadow: 0px 100px 80px rgba(0, 0, 0, 0.75),
        0px 12px 10px rgba(0, 0, 0, 0.375), inset 0px 1px 1px #5c546c;
      overflow: hidden;
      @include breakpoint(md) {
        margin-bottom: 0;
      }
    }
    .icon {
      margin-bottom: 1.2rem;
      width: 4.8rem;

      @include breakpoint(md) {
        margin-bottom: 1.6rem;
      }
    }
    a {
      position: relative;
      z-index: var(--z2);
      margin: 0.4rem 0 1rem;
      font-size: 2.2rem;
      font-size: 2.2rem;
      text-transform: capitalize;

      @include breakpoint(md) {
        margin-bottom: 1rem;
        font-size: 2rem;
        font-size: 2rem;
      }
    }
    h4 {
      font-size: 2.3rem;
      margin-bottom: 1.2rem;

      @include breakpoint(md) {
        margin-bottom: 0.6rem;
        font-size: 2.3rem;
      }
    }
    p {
      position: relative;
      z-index: var(--z2);
      margin-bottom: 2.4rem;
      font-size: 1.7rem;
      @include breakpoint(md) {
        margin-bottom: 2.8rem;
        font-size: 1.8rem;
      }
    }
    .hero {
      border-radius: 8px;
    }
  }

  h3 {
    margin-bottom: 2rem;
    font-size: 2.6rem;
    font-weight: 600;
    line-height: 1.1;
    background: linear-gradient(180deg, #ffffff 0%, #d0c4e7 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    @include breakpoint(md) {
      margin-bottom: 1.6rem;
    }
  }
</style>

<script>
  export default {
    data: () => ({
      featuresss: null,
      features: null,
    }),
    async fetch() {
      this.featuresss = await this.$content("features", { deep: true })
        .sortBy("title", "asc")
        .where({ type: "all in one" })
        .fetch()

      this.features = await this.$content("features", { deep: true })
        .sortBy("title", "desc")
        .where({ type: "customer centric" })
        .fetch()
    },
    methods: {
      fadeIn() {
        gsap.from(".app", {
          opacity: 0,
          duration: 1.2,
          delay: 0.15,
          stagger: 0.15,
          ease: Power4.easeOut,
        })
      },
    },
    mounted() {
      this.fadeIn()
    },
  }
</script>
