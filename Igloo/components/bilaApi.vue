<template>
    <div v-for="product in products" class="w-fit xl:w-2/3 lg:w-11/12 md:w-fit pr-0 ml-10 xl:ml-96 lg:ml-24 mt-16 items-center shadow-sm mr-7 justify-items-center bg-white rounded-md">
        <div class=" border w-full overflow-hidden mb-5 cursor-pointer h-auto rounded-md">
          <div  class="md:flex max-h-full inline-block">
            <div class=" col-auto justify-end md:w-[500px] w-fit pr-2">
                <div class=" h-2/3">
                    <img :src="product.image" alt="" class="  w-auto h-36 m-4 shadow">
                </div>
              <div class="mt-6 ml-4 flex">
                <p class="mr-2 text-[14px]">J.</p>
                <icon name="material-symbols:kid-star-outline-sharp" class=" mr-1 mt-1 text-slate-500"/>
                <icon name="material-symbols:kid-star-outline-sharp" class=" mr-1 mt-1 text-slate-500"/>
                <icon name="material-symbols:kid-star-outline-sharp" class=" mr-1 mt-1 text-slate-500"/>
                <icon name="material-symbols:kid-star-outline-sharp" class=" mr-1 mt-1 text-slate-500"/>
                <icon name="material-symbols:kid-star-outline-sharp" class=" mr-1 mt-1 text-slate-500"/>
                <p class=" text-[12px] text-slate-500 mt-1 ml-1">(0)</p>
                <p class=" bg-gray-200 rounded-xl p-1 m-0 text-[11px] ml-3">Individual</p>
              </div>
            </div>
            <div class=" ml-2 p-4 flex flex-col w-full">
              <div class=" flex justify-between items-center">
                <h1 class="font-bold text-xl text-[rgba(58,60,62,255)]">{{ product.title }}</h1>
                <div class="flex">
                  <h1 class=" w-20 text-end font-bold text-[rgba(58,60,62,255)]">{{ product.price}}</h1>
                  <p class=" font-mono ml-1 font-bold">$</p>
                </div>  
              </div>
              <div class="flex justify-between items-center ">
                <p class=" text-[11px] text-neutral-600 font-light w-3/4 mt-3 border-t-2">{{ product.description }}</p>
                  <p class=" text-[14px] mb-[2px] text-[rgba(58,60,62,255)]">Good price <Icon name="fe:info" class="mb-1"/></p>
                </div>
                <div class="flex justify-end">
                  <button class="border rounded-md bg-[rgba(198,227,191,255)] text-xs h-2.5 w-8"></button>
                  <button class="border rounded-md bg-[rgba(140,199,125,255)] text-xs h-2.5 w-8"></button>
                  <button class="border rounded-md bg-[rgba(81,131,68,255)] text-xs h-2.5 w-8"></button>
                </div>
                <div class="flex justify-between mt-3">
                  <div class="flex">
                    <p class=" text-xs text-neutral-600"><icon name="material-symbols-light:category-outline" class=" mr-1 text-lg"/>{{ product.category }}</p>
                    
                  </div>
                  <div class="md:flex ">
                    <p class="text-xs">from 40 000 </p><p class="text-xs font-mono ml-1 mr-1">ISK</p><p class="text-xs"> monthly payment</p>
                  </div>
                </div>
                <div class="mt-5">
                  <p class=" text-xs text-neutral-600">Kópavogur</p>
                  <p class=" mt-2 text-xs text-neutral-600">Posted 1 day ago</p>
                </div>
                <div class=" flex justify-end">
                  <icon name="emojione:red-heart" class=" text-xl"/>
                </div>
            </div>
          </div>
        </div>
    </div>
</template>

<script setup>
const {data: products} = await useFetch('https://fakestoreapi.com/products');
</script>