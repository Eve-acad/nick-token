<template>
  <div class="flex justify-center w-full pt-5">
    <img class="h-20" src="@/assets/logo.png" />
  </div>
  <div class="flex flex-col px-2 container mx-auto py-3">
  <div class="flex flex-wrap justify-center mx-auto w-full">
    <div class="grid grid-cols-2 lg:w-1/4 w-96 bg-orange-600">
      <div class="py-1 pl-2">
        <a class="hover-underline font" href="https://shorturl.at/fnqLU">TONIGHT'S SPECIAL</a>
      </div>
      <div class="bg-yellow-600 py-1 pl-7 font">
Time: {{ currentTime }}
      </div>
    </div>

    <div class="bg-yellow-500 px-3 py-1 font">
      <a href="https://raydium.io/swap/?outputCurrency=6XKKsryzoUjewxyQ3P4ZCZuVT1YnsY2bvQpJt7tNR49n" class="hover-underline ">Buy $NICKELODEON</a>
    </div>
    <div class="flex flex- gap-4 bg-gray-400 pl-8 pr-8 py-1 font">
        <div><a href="https://solscan.io/token/6XKKsryzoUjewxyQ3P4ZCZuVT1YnsY2bvQpJt7tNR49n" class="hover-underline"><strong>SOLSCAN</strong></a></div>
        <div><a href="https://birdeye.so/token/6XKKsryzoUjewxyQ3P4ZCZuVT1YnsY2bvQpJt7tNR49n?chain=solana" class="hover-underline"><strong>BIRDEYE</strong></a></div>
        <div><a href="https://rugcheck.xyz/tokens/6XKKsryzoUjewxyQ3P4ZCZuVT1YnsY2bvQpJt7tNR49n" class="hover-underline"><strong>RUGCHECK</strong></a></div>
        <div><a href="https://twitter.com/nickelodeon_SOL" class="hover-underline"><strong>TWITTER</strong></a></div>
        <div><a href="https://t.me/nickelodeon_SOL" class="hover-underline"><strong>TELEGRAM</strong></a></div>
      </div>
    <div class="flex bg-gray-300 px-3 py-1 font">
      <div class="pr-3">SEARCH</div>
      <input type="text" class="border outline-none" placeholder="Vibes and Cartoon" />
      <div class="pl-3"><button>GO</button></div>
    </div>
  </div>

    <div class="flex flex-col md:grid grid-cols-9 gap-4 mt-5">

      <div class="flex flex-col w-full md:w-fit gap-4 md:col-span-2">
        <div class="bg-black p-2">
          <img src="@/assets/a.jpg" />
        </div>
        <div class="bg-black p-2">
          <img src="@/assets/ad1.gif" />
        </div>

        <div class="bg-black p-2">
          <img src="@/assets/ad3.gif" class="w-full  md:h-52" />
        </div>
        <div class="bg-black p-2">
          <img src="@/assets/c.png" class="w-full md:h-44" />
        </div>
      </div>

      <div class="flex flex-col gap-3 w-full md:col-span-7">
        <div class="w-full grid grid-cols-5 gap-3">
          <div class="col-span-4 border">
            <video controls autoplay muted class="w-full">
    <source src="@/assets/Intro.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>


          </div>
          <img src="@/assets/e.jpeg" class="w-full h-full" />
        </div>
        <div class="w-full grid grid-cols-5 gap-3">
          <div class="border"><img src="@/assets/f.jpg" class="w-full h-52" /></div>
          <div class="border col-span-3"><img src="@/assets/d.png" class="w-full h-52" /></div>
          <div class="border"><img src="@/assets/ad4.png" class="w-full h-52" /></div>
        </div>
        <div class="w-full grid grid-cols-5 gap-3">
          <div class="border"><img src="@/assets/ad2.gif" class="w-full h-28" /></div>
          <div class="border col-span-3"><img src="@/assets/ad5.gif" class="w-full h-28" /></div>
          <div class=""><img src="@/assets/logo.png" class="w-full h-28" /></div>
        </div>
        <div class="flex flex-col text-sm">
          <div> > <a class="hover-underline">PRIVACY POLICY</a></div>
          <div class="flex gap-1.5 flex-wrap">
            <div>> <a class="hover-underline">TRADEMARK INFORMATION</a></div>
            <div>> <a class="hover-underline">TERMS OF USE</a></div>
            <div>> <a class="hover-underline">PARENT GUIDE</a></div>
            <div>> <a class="hover-underline">TV PARENTAL GUIDELINES</a></div>
          </div>
          <div> @2024 $NICK Token. We Are Not Affiliated With The Official Nickelodeon. Everything here is NFA</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.hover-underline:hover {
  text-decoration: underline;
}

body{
  background-color: #EDB829
}

.font{
  font-family: 'Rubik Bubbles';
}
</style>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

const currentTime = ref(getCurrentTime());

function getCurrentTime() {
  const now = new Date();
  const hours = now.getHours();
  const minutes = now.getMinutes();
  return `${padZero(hours)}:${padZero(minutes)} ${hours >= 12 ? 'PM' : 'AM'}`;
}

function padZero(number: number) {
  return number < 10 ? `0${number}` : number;
}

onMounted(() => {
  setInterval(() => {
    currentTime.value = getCurrentTime();
  }, 60000); // Update every minute
});
</script>
