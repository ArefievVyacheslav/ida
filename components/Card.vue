<template>
  <div class="product-wrapper">
    <img :src="product.img" alt="product image" class="product-image">
    <h3 class="product-name">{{ product.name }}</h3>
    <span class="product-description">{{ product.description }}</span>
    <span class="product-price">{{ product.price }} руб.</span>
    <svg @click="removeProduct(productIndex)" class="delete-btn" width="40" height="40" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg"><g filter="url(#filter0_d_4_347)"><rect x="4" y="2" width="32" height="32" rx="10" fill="#FF8484"/></g><g clip-path="url(#clip0_4_347)"><path d="M22.207 15.7969C22 15.7969 21.8322 15.9646 21.8322 16.1716V23.2535C21.8322 23.4604 22 23.6283 22.207 23.6283C22.4139 23.6283 22.5817 23.4604 22.5817 23.2535V16.1716C22.5817 15.9646 22.4139 15.7969 22.207 15.7969Z" fill="white"/><path d="M17.7854 15.7969C17.5785 15.7969 17.4107 15.9646 17.4107 16.1716V23.2535C17.4107 23.4604 17.5785 23.6283 17.7854 23.6283C17.9924 23.6283 18.1602 23.4604 18.1602 23.2535V16.1716C18.1602 15.9646 17.9924 15.7969 17.7854 15.7969Z" fill="white"/><path d="M14.5629 14.7634V23.9953C14.5629 24.541 14.763 25.0534 15.1126 25.4211C15.4605 25.7898 15.9447 25.9991 16.4514 26H23.541C24.0478 25.9991 24.532 25.7898 24.8798 25.4211C25.2293 25.0534 25.4294 24.541 25.4294 23.9953V14.7634C26.1242 14.5789 26.5745 13.9077 26.4815 13.1947C26.3884 12.4819 25.7811 11.9487 25.0622 11.9485H23.1437V11.4801C23.1459 11.0863 22.9902 10.708 22.7113 10.4298C22.4325 10.1517 22.0537 9.99683 21.6598 10H18.3325C17.9387 9.99683 17.5599 10.1517 17.281 10.4298C17.0022 10.708 16.8465 11.0863 16.8487 11.4801V11.9485H14.9302C14.2112 11.9487 13.6039 12.4819 13.5108 13.1947C13.4179 13.9077 13.8681 14.5789 14.5629 14.7634ZM23.541 25.2506H16.4514C15.8107 25.2506 15.3124 24.7002 15.3124 23.9953V14.7963H24.68V23.9953C24.68 24.7002 24.1816 25.2506 23.541 25.2506ZM17.5981 11.4801C17.5956 11.285 17.6723 11.0972 17.8107 10.9595C17.9491 10.8218 18.1373 10.7461 18.3325 10.7495H21.6598C21.8551 10.7461 22.0433 10.8218 22.1816 10.9595C22.3201 11.0971 22.3968 11.285 22.3943 11.4801V11.9485H17.5981V11.4801ZM14.9302 12.6979H25.0622C25.4347 12.6979 25.7367 12.9999 25.7367 13.3724C25.7367 13.7449 25.4347 14.0469 25.0622 14.0469H14.9302C14.5577 14.0469 14.2557 13.7449 14.2557 13.3724C14.2557 12.9999 14.5577 12.6979 14.9302 12.6979Z" fill="white"/><path d="M19.9962 15.7969C19.7892 15.7969 19.6215 15.9646 19.6215 16.1716V23.2535C19.6215 23.4604 19.7892 23.6283 19.9962 23.6283C20.2032 23.6283 20.3709 23.4604 20.3709 23.2535V16.1716C20.3709 15.9646 20.2032 15.7969 19.9962 15.7969Z" fill="white"/></g><defs><filter id="filter0_d_4_347" x="0" y="0" width="40" height="40" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dy="2"/><feGaussianBlur stdDeviation="2"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.1 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_4_347"/><feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_4_347" result="shape"/></filter><clipPath id="clip0_4_347"><rect width="16" height="16" fill="white" transform="translate(12 10)"/></clipPath></defs></svg>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ['product', 'productIndex'],
  methods: {
    removeProduct(productIndex) {
      this.$store.commit('removeProduct', productIndex)
    }
  }
}
</script>

<style scoped lang="sass">
.product-wrapper
  position: relative
  max-width: 332px
  max-height: 423px
  box-shadow: 0 20px 30px rgba(0, 0, 0, 0.04), 0 6px 10px rgba(0, 0, 0, 0.02)
  border-radius: 4px

.product-wrapper:hover .delete-btn
  display: initial

.product-wrapper:hover
  cursor: url('assets/cursor.svg'), pointer

.product-image
  width: 332px
  height: 200px
  object-fit: cover
  border-radius: 4px 4px 0 0

.product-name,
.product-description,
.product-price
  margin: 16px
  font-family: Source Sans Pro
  color: #3F3F3F

.product-name,
.product-price
  font-weight: 600

.product-description,
.product-price
  display: block

.product-name
  font-size: 20px
  line-height: 25px

.product-description
  font-weight: normal
  font-size: 16px
  line-height: 20px

.product-price
  font-style: normal
  font-size: 24px
  line-height: 30px
  padding-bottom: 24px


.delete-btn
  position: absolute
  top: -8px
  right: -8px
  display: none

</style>
