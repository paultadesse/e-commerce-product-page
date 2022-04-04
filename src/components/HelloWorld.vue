<template>
  <div class="md:px-44">
    <!-- navigation bar -->
    <div class="flex justify-between items-center p-6 md:p-0 md:my-6">
      <div class="flex items-center space-x-2">
        <img class="lg:hidden" src="../assets/icon-menu.svg" alt="" srcset="" />
        <img src="../assets/logo.svg" alt="" srcset="" />
        <div class="hidden lg:block pl-16 space-x-6">
          <a href="#">Collections</a>
          <a href="#">Men</a>
          <a href="#">Women</a>
          <a href="#">About</a>
          <a href="#">Contact</a>
        </div>
      </div>
      <div class="flex items-center space-x-6">
        <div class="relative">
          <img src="../assets/icon-cart.svg" alt="" srcset="" />
          <div class="absolute px-2.5 text-xs text-white rounded-full left-2 -top-2 bg-orange">
            <p>3</p>
          </div>
        </div>
        <img class="h-7 md:h-12 w-auto" src="../assets/image-avatar.png" alt="" srcset="" />
      </div>
    </div>
    <hr class="hidden md:block mt-3 py-6 mx-auto">

    <!-- whole content -->
    <div class="md:flex md:justify-center md:items-center md:space-x-24 md:px-28 md:mt-16">
      <!-- image holder -->
      <div class="relative md:max-w-lg flex-none">
        <div class="md:hidden absolute top-1/2 inset-x-0 flex items-center justify-between px-4">
          <div class="relative bg-white h-10 w-10 rounded-full">
            <img class="absolute left-3 top-3" src="../assets/icon-previous.svg" alt="" srcset="" />
          </div>
          <div class="relative bg-white h-10 w-10 rounded-full">
            <img class="absolute right-3 top-3" src="../assets/icon-next.svg" alt="" srcset="" />
          </div>
        </div>
        <!-- product image -->
        <div>
          <!-- big image -->
          <img class="md:rounded-2xl" src="../assets/image-product-1.jpg" alt="" srcset="" />
          <div class="hidden md:flex justify-between pt-2 md:pt-10">
            <!-- selected image -->
            <div class="md:rounded-lg border-2 border-orange bg-paleOrange ">  
              <img class="opacity-25 h-24 " src="../assets/image-product-1-thumbnail.jpg" alt="" srcset="" />
            </div>
            <div class="">  
              <img class="md:rounded-lg h-24 " src="../assets/image-product-2-thumbnail.jpg" alt="" srcset="" />
            </div>
            <div class="">  
              <img class="md:rounded-lg h-24 " src="../assets/image-product-3-thumbnail.jpg" alt="" srcset="" />
            </div>
            <div class="">  
              <img class="md:rounded-lg h-24 " src="../assets/image-product-4-thumbnail.jpg" alt="" srcset="" />
            </div>
          </div>
        </div>
      </div>

    <div class="p-6  md:max-w-lg">
        <!-- company name -->
        <div>
          <p class="uppercase text-orange leading-relaxed tracking-widest font-semibold">sneaker company</p>
        </div>
        <!-- short description -->
        <div class="py-3 md:py-6">
          <p class="tracking-wide text-2xl font-semibold md:text-4xl">
            Fall Limited Edition Sneakers
          </p>
        </div>
        <!-- large discription -->
        <div>
          <p class="text-darkGrayishBlue font-light tracking-wide">These low-profile sneaker are your perfect casual wear companion. Featuring a durable rubber outer sole, they'll withstand everything the weather can offer.</p>
        </div>
        <!-- pricing -->
        <div class="py-6 flex justify-between items-center md:flex-col md:justify-start md:items-start">
          <div class="flex items-center space-x-4">
            <p class="text-3xl font-bold">$125.00</p>
            <div class="bg-paleOrange rounded">
              <p class="px-2 text-orange text-lg font-bold">50%</p>
            </div>
          </div>
          <div>
            <p class="line-through text-lg font-bold text-grayishBlue">$250.00</p>
          </div>
        </div>
        <div class="md:flex md:space-y-0 space-y-4 md:space-x-4">
          <!-- quantity control -->
          <div class="flex md:w-1/2 flex-none items-center justify-between bg-lightGrayishBlue rounded-lg px-4 py-3">
            <img class="" src="../assets/icon-minus.svg" alt="" srcset="" />
            <p class="font-bold text-lg">0</p>
            <img class="" src="../assets/icon-plus.svg" alt="" srcset="" />
          </div>
          <!-- add to cart button -->
          <div class="md:w-full flex-none">
            <button class="flex w-full items-center justify-center bg-orange space-x-4 rounded-lg px-4 py-4">
              <img class="" src="../assets/icon-cart.svg" alt="" srcset="" />
              <p class="font-semibold text-white tracking-wide text-sm">Add to cart</p>
            </button>
          </div>
        </div>
      </div>
    </div> 
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
