<template>
  <div id="app">
    <div class="header">
      <p class="heading-xl">
        <span class="thin">Reliable, efficient delivery</span>
        <br />
        <span class="bold">Powered by Technology</span>
      </p>
      <p class="text">
        Our Artificial Intelligence powered tools use millions of project data
        points to ensure that your project is successful
      </p>
    </div>
    <div class="cards flex s-dir-col">
      <div class="wid-33 column resp s-wid-100">
        <div class="flex h-full ai-center">
          <card
            v-bind:heading="cardOne.heading"
            v-bind:text="cardOne.text"
            v-bind:img="cardOne.img"
            v-bind:color="cardOne.color"
          ></card>
        </div>
      </div>
      <div class="wid-33 column resp s-wid-100">
        <div class="flex dir-col jc-center ai-center">
          <card
            v-bind:heading="cardTwo.heading"
            v-bind:text="cardTwo.text"
            v-bind:img="cardTwo.img"
            v-bind:color="cardTwo.color"
          ></card>
          <card
            v-bind:heading="cardThree.heading"
            v-bind:text="cardThree.text"
            v-bind:img="cardThree.img"
            v-bind:color="cardThree.color"
          ></card>
        </div>
      </div>
      <div class="wid-33 column resp s-wid-100">
        <div class="flex h-full jc-end ai-center">
          <card
            v-bind:heading="cardFour.heading"
            v-bind:text="cardFour.text"
            v-bind:img="cardFour.img"
            v-bind:color="cardFour.color"
          ></card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    Card
  },
  data() {
    return {
      cardOne: {
        heading: "Supervisor",
        text: "Monitors activity to identify project roadblocks",
        img: {
          src: "./images/icon-supervisor.svg",
          alt: "supervisor",
          title: "supervisor"
        },
        color: "cyan"
      },
      cardTwo: {
        heading: "Team Builder",
        text:
          "Scans our talent network to create the optimal team for your project",
        img: {
          src: "./images/icon-team-builder.svg",
          alt: "team-builder",
          title: "team-builder"
        },
        color: "red"
      },
      cardThree: {
        heading: "Karma",
        text: "Regularly evaluates our talent to ensure quality",
        img: {
          src: "./images/icon-karma.svg",
          alt: "karma",
          title: "karma"
        },
        color: "orange"
      },
      cardFour: {
        heading: "Calculator",
        text:
          "Uses data from past projects to provide better delivery estimates",
        img: {
          src: "./images/icon-calculator.svg",
          alt: "calculator",
          title: "calculator"
        },
        color: "blue"
      }
    };
  }
};
</script>

<style lang="scss">
$veryDarkBlue: hsl(234, 12%, 34%);
$grayishBlue: hsl(229, 6%, 66%);
@mixin resp() {
  @media (max-width: "370px") {
    @content;
  }
}

.header {
  text-align: center;
  padding: 77px 0 48px;
  .heading-xl {
    font-size: 2.25rem;
    line-height: 3.4rem;
    color: $veryDarkBlue;
    padding-left: 1rem;
    @include resp() {
      line-height: 3rem;
      font-size: 1.5rem;
      padding-left: 0;
    }
    .thin {
      font-weight: 200;
    }
    .bold {
      font-weight: 700;
      @include resp() {
        display: block;
        margin-top: -0.5rem;
      }
    }
  }
  .text {
    padding: 1rem 28rem;
    color: $grayishBlue;
    @include resp() {
      line-height: 1.5rem;
      padding: 0.5rem 2rem;
    }
  }
}
.cards {
  padding: 0 9.4rem 0 10.3rem;
  @include resp() {
    padding: 1.3rem 1.5rem 0rem 2.1rem;
  }
}
</style>
