<template>
  <div class="">
    <!-- Mobile Menu -->
      <div v-if="toggleNavBar" class="xl:hidden">
        <div class="absolute bg-black z-40 h-screen w-full opacity-40" @click="toggleNavBar = false"> </div>
        <div class="absolute z-50 bg-white h-screen w-8/12 p-6">
          <div class="mb-10">
            <img class="cursor-pointer h-4" @click="toggleNavBar = false" src="../assets/icon-close-black.svg" alt="" srcset="" />
          </div>
          <div class="space-y-6 text-xl font-bold">
            <div>Collections</div>
            <div>Men</div>
            <div>Women</div>
            <div>About</div>
            <div>Contact</div>
          </div>
        </div>
      </div>
    <!-- lightbox design -->
    <div v-if="showLightBox" class="hidden xl:block">
      <div class="absolute z-40 inset-0  flex justify-center items-center">
        
        <!-- images container -->
        <div class="relative max-w-lg space-y-4">
          <!-- close icon -->
        <div class="absolute bottom-full mb-5 z-40 hover:cursor-pointer max-w-lg mx-auto inset-x-0 flex justify-end ">
          <img class="cursor-pointer h-6" @click="showLightBox = !showLightBox" src="../assets/icon-close.svg" alt="" srcset="" />
        </div>
          <img class="md:rounded-2xl h-1/2" :src="img(selectedImage.path)" alt="" srcset="" />
          <div class="flex justify-around pt-4 px-6">
              <!-- selected image -->
              <div class="bg-paleOrange md:rounded-lg" v-for="(image, index) in images" :key="index">  
                <img 
                  :class="isSelected(image)
                     ? 'opacity-50 md:rounded-lg border-2 border-orange bg-paleOrange disabled':'cursor-pointer'"
                     class="md:rounded-lg h-20 hover:opacity-50" 
                     :src="img(image.thumbnailPath)" 
                     alt="" 
                     srcset=""
                     @click="!isSelected(image) ? selectImage(image) : null"
                />
              </div>
            </div>
        </div>
        <div class="absolute max-w-xl px-1 bottom-1/2 py-10 flex justify-between w-full">
            <button class="relative cursor-pointer bg-white h-12 w-12 rounded-full" @click="previousImage">
              <img class="absolute left-4 top-4"  src="../assets/icon-previous.svg" alt="" srcset="" />
            </button>
            <button class="relative cursor-pointer bg-white h-12 w-12 rounded-full" @click="nextImage">
              <img class="absolute right-4 top-4" src="../assets/icon-next.svg" alt="" srcset="" />
            </button>
          </div>
      </div>
      <!-- the black background -->
      <div class="absolute bg-black inset-0 z-20 opacity-75"></div>
    </div>
    <div class="xl:max-w-7xl max-w-lg mx-auto md:px-4">
      <!-- navigation bar -->
      <div class="relative flex justify-between items-center p-6 md:p-0 md:my-6">
        <div class="flex items-center">
          <img class="xl:hidden px-2" @click="toggleNavBar = true" src="../assets/icon-menu.svg" alt="" srcset="" />
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
          <div class="relative cursor-pointer">
            <img src="../assets/icon-cart.svg" alt="" srcset="" @click="showCart = !showCart" />
            <div class="absolute px-2.5 text-xs text-white rounded-full left-2 -top-2 bg-orange">
              <p>{{ itemsInCart }}</p>
            </div>
          </div>
          <img class="h-7 md:h-12 w-auto" src="../assets/image-avatar.png" alt="" srcset="" />
        </div>  
      </div>
      <hr class="hidden xl:block mt-3  mx-auto ">
      <!-- cart dialog -->
        <div v-if="showCart" class="relative">
          <div class="absolute z-40 px-2.5 xl:px-0 z-10 top-1 right-0 md:-bottom-0 mt-2 md:-mt-5  w-full flex md:justify-end">
            <div class="w-full xl:w-4/12 rounded-2xl">
              <div class="shadow-2xl bg-white rounded-2xl">
                <div class="p-6">
                  <p class="font-bold">Cart</p>
                </div>         
                <hr class="">
                <!-- items list  -->
                <div v-if="itemsInCart">
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
                            <p class="text-darkGrayishBlue font-light">$125.00 x {{ itemsInCart }} </p>
                            <p>${{ totalPrice }}</p>
                          </div>
                        </div>
                        <div class="flex-none">
                          <img class="h-5 cursor-pointer" @click="removeFromCart" src="../assets/icon-delete.svg" alt="" srcset="" />
                        </div>
                      </div>
                    </div>
                  <div class="px-6 pb-6 ">
                    <button class="block w-full py-3 rounded-lg font-bold bg-orange text-white">Checkout</button>
                  </div>
                </div>
                <div v-else class="flex h-52 justify-center items-center">
                  <p class="text-darkGrayishBlue font-bold">Your cart is empty.</p>
                </div>
              </div>
            </div>
          </div>
          <!-- cart background [covers the whole page] closes the cart list on click -->
          <div class="absolute bg-transparent z-30 cursor-pointer h-screen w-full" @click="showCart = false"></div>
        </div>
      <!-- whole content -->
      <div class="xl:flex justify-center items-center xl:space-x-24 xl:px-28 xl:mt-16">
        <!-- image holder -->
        <div class="relative md:max-w-lg flex-none">
          <!-- product image -->
              <!-- big image -->
              <div class="md:hidden">
                <button class="absolute top-1/3 mt-10 ml-4 bg-white h-10 w-10 rounded-full" @click="previousImage">
                  <img class="absolute left-3 top-3" src="../assets/icon-previous.svg" alt="" srcset="" />
                </button>
                <button class="absolute top-1/3 mt-10 mr-4 bg-white h-10 w-10 right-0 rounded-full" @click="previousImage">
                  <img class="absolute left-3 top-3" src="../assets/icon-next.svg" alt="" srcset="" />
                </button>
              </div>
              <img class="md:rounded-2xl cursor-pointer" 
                @click="showLightBox = true" 
                :src="img(selectedImage.path)" 
                alt="" 
                srcset="" />
              <div class="hidden md:flex justify-between pt-2 md:pt-10" >
                <!-- selected image -->
                <div class="" v-for="(image, index) in images" :key="index">  
                  <img :class="isSelected(image)
                     ? 'opacity-25 md:rounded-lg border-2 border-orange bg-paleOrange disabled':'cursor-pointer'"
                     class="md:rounded-lg h-24 hover:opacity-25" 
                     :src="img(image.thumbnailPath)" 
                     alt="" 
                     srcset=""
                     @click="!isSelected(image) ? selectImage(image) : null"
                  />
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
              <img class="cursor-pointer" @click="itemQuantity != 0 ? itemQuantity-- : null" src="../assets/icon-minus.svg" alt="" srcset="" />
              <p class="font-bold text-lg">{{ itemQuantity }}</p>
              <img class="cursor-pointer" @click="itemQuantity++" src="../assets/icon-plus.svg" alt="" srcset="" />
            </div>
            <!-- add to cart button -->
            <div class="w-full ">
              <button class="flex w-full items-center justify-center bg-orange space-x-4 rounded-lg px-4 py-4" @click="addToCart">
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
import { ref } from "vue";
export default {
  name: "HelloWorld",

  setup() {
    const images = [
      { name: "product-1", path: "image-product-1.jpg", thumbnailPath: "image-product-1-thumbnail.jpg" },
      { name: "product-2", path: "image-product-2.jpg", thumbnailPath: "image-product-2-thumbnail.jpg" },
      { name: "product-3", path: "image-product-3.jpg", thumbnailPath: "image-product-3-thumbnail.jpg" },
      { name: "product-4", path: "image-product-4.jpg", thumbnailPath: "image-product-4-thumbnail.jpg" },
    ];

    let selectedImage = ref(images[0]);
    let showCart = ref(false);
    let showLightBox = ref(false);
    let itemQuantity = ref(0);
    let itemsInCart = ref(0);
    let toggleNavBar = ref(false);

    return {
      images,
      selectedImage,
      showCart,
      showLightBox,
      itemQuantity,
      itemsInCart,
      toggleNavBar
    }
  },

  computed: {
    totalPrice() {
      return (this.itemsInCart * 125).toFixed(2);
    }
  },

  methods: {
    img(path) {
      return require(`../assets/${path}`);
    },

    isSelected(image) {
      return image.name === this.selectedImage.name;
    },

    selectImage(image) {
      this.selectedImage = image;
    },

    getCurrentImageIndex() {
      // There are two different approaches to [ Get the index of an Object in an Array ]
      const index = this.images.map(object => object.name).indexOf(this.selectedImage.name);
      // let currentImageindex = this.images.findIndex(object => {
      //   return object.name == this.selectedImage.name;
      // });
      // console.log(index);
      return index;
    },

    previousImage() {
      const index = this.getCurrentImageIndex();
      //show the previous image in the list until we reach the initial [ finally start from last index]
      index != 0 ? this.selectedImage = this.images[index - 1] : this.selectedImage = this.images[this.images.length - 1];
    },

    nextImage() {
      const index = this.getCurrentImageIndex();
      //show the next image in the list until we reach the end [ finally start from 0 index]
      index != this.images.length - 1 ? this.selectedImage = this.images[index + 1] : this.selectedImage = this.images[0];
    },

    addToCart() {
      this.itemsInCart = this.itemQuantity;
    },

    removeFromCart() {
      this.itemQuantity = 0; 
      this.itemsInCart = 0;
    }  
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
