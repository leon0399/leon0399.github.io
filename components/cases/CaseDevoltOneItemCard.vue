<template>
  <base-case-item-card class="case--devolt-one">
    <!-- <div
      class="block absolute w-full h-1/3 case__half bottom-0 inset-x-0 z-0"
    /> -->
    <div
      class="
        case__content
        relative
        flex flex-col
        justify-end
        w-full
        h-full
        z-10
      "
    >
      <div class="case__illustration relative h-full">
        <div class="floating-card floating-card--primary">
          <picture v-lazy-container="{ selector: 'img' }">
            <source
              :srcSet="`
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=144&format=webp')} 1x,
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=288&format=webp')} 2x,
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=432&format=webp')} 3x
              `"
              type="image/webp"
            />
            <source
              :srcSet="`
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=144')} 1x,
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=288')} 2x,
                ${require('~/assets/img/cases/devolt-one/mock-1.png?size=432')} 3x
              `"
              type="image/png"
            />
            <img
              :data-loading="
                require('~/assets/img/cases/devolt-one/mock-1.png?lqip')
              "
              :data-src="
                require('~/assets/img/cases/devolt-one/mock-1.png?size=144')
              "
              class="floating-card__inner no-blur"
              loading="lazy"
            />
          </picture>
        </div>
        <div class="floating-card floating-card--secondary">
          <picture v-lazy-container="{ selector: 'img' }">
            <source
              :srcSet="`
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=144&format=webp')} 1x,
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=288&format=webp')} 2x,
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=432&format=webp')} 3x
              `"
              type="image/webp"
            />
            <source
              :srcSet="`
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=144')} 1x,
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=288')} 2x,
                ${require('~/assets/img/cases/devolt-one/mock-2.png?size=432')} 3x
              `"
              type="image/png"
            />
            <img
              :data-loading="
                require('~/assets/img/cases/devolt-one/mock-2.png?lqip')
              "
              :data-src="
                require('~/assets/img/cases/devolt-one/mock-2.png?size=144')
              "
              class="floating-card__inner no-blur"
              loading="lazy"
            />
          </picture>
        </div>
      </div>
      <div class="text-center my-4">
        <a
          class="font-black font-montserrat text-6xl"
          href="https://devolt.one/"
        >
          D.1
        </a>
      </div>
      <div>
        <p class="text-center">
          Software development agency, oriented on
          <strong>custom-built CRM systems</strong>
        </p>
      </div>
    </div>
  </base-case-item-card>
</template>

<script>
import BaseCaseItemCard from './BaseCaseItemCard'
export default {
  name: 'CaseDevoltOneItemCard',
  components: { BaseCaseItemCard },
}
</script>

<style scoped lang="scss">
.case--devolt-one {
  position: relative;
  // background-color: #1a1a1a;
  box-shadow: 0px 20px 120px rgba(#1a1a1a, 0.1);

  .case__content {
    // mix-blend-mode: difference;
    // background-blend-mode: difference;
  }

  .case__half {
    background-color: #1a1a1a;
    border-bottom-left-radius: 1.5rem;
    border-bottom-right-radius: 1.5rem;
  }

  .floating-card {
    will-change: transform;
    transition: transform 0.3s ease;
  }
}

.floating-card {
  --animation-offset: 1;
  --size: 9rem;

  position: absolute;
  height: var(--size);
  width: var(--size);
  animation-delay: calc(0.5s * var(--animation-offset));
  z-index: 5;

  top: 50%;
  transform: translateY(-50%);

  &:nth-child(2n) {
    --animation-offset: 2;
  }

  .floating-card__inner {
    height: 100%;
    width: 100%;
    border-radius: 0.5rem;
    background-position: center center;
    background-size: cover;
    animation-delay: calc(0.5s * var(--animation-offset));
    box-shadow: 0 4px 48px rgba(0, 0, 0, 0.25);
  }

  &--animated {
    animation: float 8s ease-in-out infinite;

    .floating-card__inner {
      animation: shadow 8s ease-in-out infinite;
    }
  }

  &--primary {
    .floating-card__inner {
      background-color: #c5517d;
      transform: matrix(0.96, 0.29, -0.29, 0.96, 0, 0);
    }

    left: -1rem;
    top: calc(50% - 1rem);

    transform: translateY(-50%) translateZ(30px);
  }

  &--secondary {
    .floating-card__inner {
      background-color: #88e7c4;
      transform: matrix(0.98, -0.21, 0.2, 0.98, 0, 0);
    }

    right: -1.5rem;
    top: calc(50% + 1rem);

    transform: translateY(-50%) translateZ(45px);
  }
}
</style>
