<template>
  <md-card
    id="listingCard"
    class="md-card-login"
    :class="{ 'md-card-hidden': cardHidden }"
  >
    <md-card-header class="card-header-wrapper" :class="getClass(headerColor)">
      <slot name="title">
        @{Username} | {category}
      </slot>
      <div class="social-line">
        <slot name="title">{numNum} followers</slot>
      </div>
    </md-card-header>

    <md-card-content>
      <div class="description">
        <slot name="description">Listed: dd-mm-yyyy</slot> <br />
        <slot name="price">Price: $$$</slot>
      </div>
    </md-card-content>
  </md-card>
</template>

<style>
#listingCard {
  width: 100%;
}
.card-header-wrapper {
  background-color: #3a7571 !important;
  color: white;
}

.description {
  text-align: center;
  font-size: 1.2em;
}
</style>

<script>
export default {
  name: 'ListingCard',
  props: {
    headerColor: {
      type: String,
      default: '2e715e'
    }
  },
  data() {
    return {
      cardHidden: true
    };
  },
  beforeMount() {
    setTimeout(this.showCard, 400);
  },
  methods: {
    showCard: function() {
      this.cardHidden = false;
    },
    getClass: function(headerColor) {
      return 'md-card-header-' + headerColor + '';
    }
  }
};
</script>

<style lang="css"></style>
