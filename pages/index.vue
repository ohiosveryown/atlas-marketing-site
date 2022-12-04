<template>
  <div class="app">
    <HeaderLarge
      class="width"
      heading="Give your customers superhuman support"
      subheading="Atlas is a blazingly fast, modern support platform, helping identify and diagnose customer experience and interaction."
    />

    <main class="skew-enter">
      <section class="hero width">
        <figure>
          <img
            src="https://res.cloudinary.com/da32ufmnf/image/upload/v1668962888/atlas-refresh/index/cmk7xbfccjnfmyyr2lok.png"
            alt="Atlas Customer Timeline"
          />
        </figure>
      </section>

      <section class="features width">
        <HeaderMedium
          class="enter"
          heading="A fully integrated suite of support products"
          subheading="All of the best-in-class support tools, built specifically for support teams."
        />

        <ul class="feature-grid">
          <li class="card" v-for="feature of features" :key="feature.slug">
            <img class="icon" :src="`${feature.icon}`" />
            <NuxtLink :to="'/features/' + feature.slug">
              <h3 class="inter">{{ feature.header }}</h3>
              <p class="dark">{{ feature.subheader }}</p>
            </NuxtLink>
            <img class="hero" :src="`${feature.hero}`" />
          </li>
        </ul>
      </section>

      <section class="app-preview width">
        <HeaderMedium
          heading="Customer Centric Productivity"
          subheading="Build relationships with your customers by seeing them in their full context.
          Check it out below 👇"
        />

        <app-preview />
      </section>

      <section class="ux width">
        <HeaderMedium
          heading="A Modern Tool with a Modern User Experience"
          subheading="Finally a fast, simple UI. Rich hotkeys, a command palette, and AI accelerated productivity tools."
        />

        <ux-features class="scroll-target" />
      </section>

      <section class="signup width">
        <signup
          class="scroll-target"
          heading="Work smarter. Get started today."
          subheading="Sign up today and make customer interaction easier, and smarter."
        />
      </section>
    </main>
  </div>
</template>

<style lang="scss" scoped>
  @import "~static/style/grid.scss";

  section.hero {
    margin-bottom: 4.8rem;
    @include breakpoint(md) {
      margin-bottom: 12rem;
    }
  }

  section.features {
    margin-bottom: 4.8rem;
    @include breakpoint(md) {
      margin-bottom: 9.6rem;
    }
    header {
      margin-bottom: 2.4rem;
      text-align: center;
      @include breakpoint(md) {
        text-align: left;
        margin-bottom: 4.8rem;
        width: grid-width(5);
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
        width: 5.2rem;
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
    h3 {
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

  section.app-preview {
    margin-bottom: 6.4rem;
    @include breakpoint(md) {
      margin-bottom: 14rem;
    }
    header {
      margin-bottom: 2.4rem;
      text-align: center;
      @include breakpoint(md) {
        margin: 0 auto 4.8rem;
        width: grid-width(6.4);
      }
    }
  }

  section.ux {
    margin-bottom: 6.4rem;
    @include breakpoint(md) {
      margin-bottom: 9.6rem;
    }
    header {
      text-align: center;
      margin-bottom: 2.4rem;
      @include breakpoint(md) {
        text-align: left;
        margin-bottom: 4.8rem;
        width: grid-width(6);
      }
    }
  }
</style>

<script>
  export default {
    data: () => ({
      features: null,
    }),
    async fetch() {
      this.features = await this.$content("features", { deep: true })
        .sortBy("title", "asc")
        .fetch()
    },
    methods: {
      enter() {
        gsap.from(".skew-enter", {
          opacity: 0,
          duration: 1.2,
          delay: 0.15,
          stagger: 0.15,
          skewY: 10,
          y: 120,
          ease: Power4.easeOut,
        })
      },
      handleScroll() {
        const observerOptions = {
          root: null,
          threshold: 0,
          rootMargin: "0px 0px -240px 0px",
        }
        const observerCallback = (entries, observer) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add("active")
            }
          })
        }
        const observer = new IntersectionObserver(
          observerCallback,
          observerOptions
        )
        const targets = document.querySelectorAll(".scroll-target")
        targets.forEach((e) => observer.observe(e))
      },
    },
    mounted() {
      this.enter(), this.handleScroll()
    },
  }
</script>
