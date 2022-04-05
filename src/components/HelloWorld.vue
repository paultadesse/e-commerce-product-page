<template>
  <div class="">
    <!-- lightbox design -->
    <div class="hidden">
      <div class="absolute z-40 inset-0  flex justify-center items-center">
        <!-- close icon -->
        <div class="absolute z-40 hover:cursor-pointer top-32  max-w-lg mx-auto inset-x-0 flex justify-end ">
          <img class="cursor-pointer h-6" src="../assets/icon-close.svg" alt="" srcset="" />
        </div>
        <!-- images container -->
        <div class="max-w-lg space-y-4">
          <img class="md:rounded-2xl h-1/2" src="../assets/image-product-1.jpg" alt="" srcset="" />
          <div class="flex justify-around pt-4 px-6">
              <!-- selected image -->
              <div class="md:rounded-lg border-2 border-orange bg-paleOrange ">  
                <img class="opacity-25 h-20" src="../assets/image-product-1-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-20 hover:opacity-25" src="../assets/image-product-2-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-20 hover:opacity-25" src="../assets/image-product-3-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-20 hover:opacity-25" src="../assets/image-product-4-thumbnail.jpg" alt="" srcset="" />
              </div>
            </div>
        </div>
        <div class="absolute max-w-xl px-1 bottom-1/2 py-10 flex justify-between w-full">
            <div class="relative cursor-pointer bg-white h-12 w-12 rounded-full">
              <img class="absolute left-4 top-4" src="../assets/icon-previous.svg" alt="" srcset="" />
            </div>
            <div class="relative cursor-pointer bg-white h-12 w-12 rounded-full">
              <img class="absolute right-4 top-4" src="../assets/icon-next.svg" alt="" srcset="" />
            </div>
          </div>
      </div>
      <!-- the black background -->
      <div class="absolute bg-black inset-0 z-20 opacity-75"></div>
    </div>
    <div class="xl:max-w-7xl max-w-lg mx-auto md:px-4">
      <!-- navigation bar -->
      <div class="relative flex justify-between items-center p-6 md:p-0 md:my-6">
        <div class="flex items-center">
          <img class="xl:hidden px-2" src="../assets/icon-menu.svg" alt="" srcset="" />
          <img src="../assets/logo.svg" alt="" srcset="" />
          <div class="hidden xl:block pl-16 space-x-6 text-darkGrayishBlue font-light">
            <a href="#" class="border-opacity-0 border-b-4 border-orange py-9 hover:border-opacity-100">Collections</a>
            <a href="#" class="border-opacity-0 border-b-4 border-orange py-9 hover:border-opacity-100">Men</a>
            <a href="#" class="border-opacity-0 border-b-4 border-orange py-9 hover:border-opacity-100">Women</a>
            <a href="#" class="border-opacity-0 border-b-4 border-orange py-9 hover:border-opacity-100">About</a>
            <a href="#" class="border-opacity-0 border-b-4 border-orange py-9 hover:border-opacity-100">Contact</a>
          </div>
        </div>
        <div class="flex items-center space-x-6 md:space-x-16">
          <div class="relative">
            <img src="../assets/icon-cart.svg" alt="" srcset="" />
            <div class="absolute px-2.5 text-xs text-white rounded-full left-2 -top-2 bg-orange">
              <p>3</p>
            </div>
          </div>
          <img class="h-7 md:h-12 w-auto" src="../assets/image-avatar.png" alt="" srcset="" />
        </div>  
      </div>
      <hr class="hidden xl:block mt-3  mx-auto ">
      <!-- cart dialog -->
        <div class="relative hidden">
          <div class="absolute px-2.5 xl:px-0 z-10 top-1 right-0 md:-bottom-0 mt-2 md:-mt-5  w-full flex md:justify-end">
            <div class="w-full xl:w-4/12 rounded-2xl">
              <div class=" shadow-2xl bg-white rounded-2xl">
                <div class="p-6">
                  <p class="font-bold">Cart</p>
                </div>         
                <hr class="">
                <!-- items list  -->
                <div class="max-h-52 overflow-y-auto">
                  <div class="p-6 flex justify-between items-center">
                    <div class="flex-none">
                      <img class="rounded-lg h-14" src="../assets/image-product-1-thumbnail.jpg" alt="" srcset="" />
                    </div>
                    <div class="w-7/12">
                      <div >
                        <p class="text-darkGrayishBlue font-light truncate ">Autumn Limited Edition. this text will be not displayed because it's too long'</p>
                      </div>
                      <div class="flex space-x-2">
                        <p class="text-darkGrayishBlue font-light">$125 x 3 </p>
                        <p>$375.00</p>
                      </div>
                    </div>
                    <div class="flex-none">
                      <img class="h-5 cursor-pointer" src="../assets/icon-delete.svg" alt="" srcset="" />
                    </div>
                  </div>
                </div>
                <div class="px-6 pb-6 ">
                  <button class="block w-full py-3 rounded-lg font-bold bg-orange text-white">Checkout</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      <!-- whole content -->
      <div class="xl:flex justify-center items-center xl:space-x-24 xl:px-28 xl:mt-16">
        <!-- image holder -->
        <div class="relative md:max-w-lg flex-none">
          <div class="md:hidden absolute top-1/3 py-10 inset-x-0 flex items-center justify-between px-4">
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
            <img class="md:rounded-2xl cursor-pointer" src="../assets/image-product-1.jpg" alt="" srcset="" />
            <div class="hidden md:flex justify-between pt-2 md:pt-10">
              <!-- selected image -->
              <div class="md:rounded-lg border-2 border-orange bg-paleOrange ">  
                <img class="opacity-25 h-24 " src="../assets/image-product-1-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-24 hover:opacity-25" src="../assets/image-product-2-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-24 hover:opacity-25" src="../assets/image-product-3-thumbnail.jpg" alt="" srcset="" />
              </div>
              <div class="cursor-pointer">  
                <img class="md:rounded-lg h-24 hover:opacity-25" src="../assets/image-product-4-thumbnail.jpg" alt="" srcset="" />
              </div>
            </div>
          </div>
        </div>

      <div class="px-6 md:p-0 mt-6 2xl:mt-0 2xl:px-0 2xl:max-w-lg ">
          <!-- company name -->
          <div>
            <p class="uppercase text-sm 2xl:text-lg text-orange leading-relaxed tracking-widest font-semibold">sneaker company</p>
          </div>
          <!-- short description -->
          <div class="py-3 lg:py-6">
            <p class="tracking-wide text-2xl font-semibold 2xl:text-4xl">
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
          <div class="2xl:flex 2xl:space-y-0 space-y-4 2xl:space-x-4">
            <!-- quantity control -->
            <div class="flex w-full 2xl:w-1/3 flex-none items-center justify-between bg-lightGrayishBlue rounded-lg px-4 py-3">
              <img class="cursor-pointer" src="../assets/icon-minus.svg" alt="" srcset="" />
              <p class="font-bold text-lg">0</p>
              <img class="cursor-pointer" src="../assets/icon-plus.svg" alt="" srcset="" />
            </div>
            <!-- add to cart button -->
            <div class="w-full ">
              <button class="flex w-full items-center justify-center bg-orange space-x-4 rounded-lg px-4 py-4">
                <img class="" src="../assets/icon-cart-white.svg" alt="" srcset="" />
                <p class="font-semibold text-white tracking-wide text-sm">Add to cart</p>
              </button>
            </div>
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
