<template>
  <div v-bind:class="color" class="card">
    <p class="card_heading">
      {{ heading }}
    </p>
    <p class="card_text">
      {{ text }}
    </p>
    <img
      class="card_img"
      v-bind:src="img.src"
      v-bind:alt="img.alt"
      v-bind:title="img.title"
    />
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    heading: String,
    text: String,
    color: String,
    img: Object
  }
};
</script>

<style scoped lang="scss">
$Red: hsl(0, 78%, 62%);
$Cyan: hsl(180, 62%, 55%);
$Orange: hsl(34, 97%, 64%);
$Blue: hsl(212, 86%, 64%);
$grayishBlue: hsl(229, 6%, 66%);
@mixin resp() {
  @media (max-width: 370px) {
    @content;
  }
}
.card {
  width: 21.9rem;
  height: 15.7rem;
  border-radius: 8px;
  background-color: white;
  position: relative;
  padding-left: 2.1rem;
  margin-bottom: 1.8rem;
  box-shadow: 0px 5px 20px -5px rgba(76, 78, 97, 0.5);
  &.cyan {
    border-top: 5px solid $Cyan;
  }
  &.red {
    border-top: 5px solid $Red;
  }
  &.orange {
    border-top: 5px solid $Orange;
  }
  &.blue {
    border-top: 5px solid $Blue;
  }
  @include resp() {
    width: 19.3rem;
    height: 13.9rem;
    padding-left: 1.7rem;
    margin-bottom: 1.5rem;
  }
  &_heading {
    padding: 1.75rem 0 0;
    font-size: 18px;
    font-weight: 700;
    color: black;
    word-spacing: 0.4rem;
    @include resp() {
      padding-top: 1.5rem;
    }
  }
  &_text {
    font-size: 12px;
    padding: 0.9rem 3rem 0 0;
    line-height: 20px;
    color: $grayishBlue;
    @include resp() {
      padding-top: 0.5rem;
    }
  }
  &_img {
    position: absolute;
    width: 4rem;
    height: 4rem;
    bottom: 2rem;
    right: 2rem;
    @include resp() {
      width: 3.5rem;
      height: 3.5rem;
      bottom: 1.75rem;
      right: 1.8rem;
    }
  }
}
</style>
