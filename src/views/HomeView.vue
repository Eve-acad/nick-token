<template>
  <img class="w-100 h-20 ml-2 mt-2" src="@/assets/logo.png">
  <div class="flex flex-col px-2 container mx-auto py-3">
    <div class="flex flex-wrap">
      <div class="grid grid-cols-2 lg:w-1/4 w-96 bg-orange-600">
        <div class="py-1 pl-2"><a class="hover-underline" href="https://shorturl.at/fnqLU"><strong>TONIGHT'S
              SPECIAL</strong></a></div>
        <div class="bg-yellow-600 py-1 pl-2"><strong>Current time: {{ currentTime }}</strong></div>
      </div>

      <div class="bg-yellow-500 px-3 py-1"><a href="https://raydium.io/swap/?outputCurrency=Ah6KcTtLqrwxQwDQVAUYxKzb4yQJroDo1RrYwqYF4Lb9" class="hover-underline"><strong>$CN on SOL</strong></a></div>
      <div class="flex flex- gap-4 bg-gray-400 pl-8 pr-8 py-1">
        <div><a href="https://solscan.io/token/Ah6KcTtLqrwxQwDQVAUYxKzb4yQJroDo1RrYwqYF4Lb9" class="hover-underline"><strong>SOLSCAN</strong></a></div>
        <div><a href="https://birdeye.so/token/Ah6KcTtLqrwxQwDQVAUYxKzb4yQJroDo1RrYwqYF4Lb9?chain=solana" class="hover-underline"><strong>BIRDEYE</strong></a></div>
        <div><a href="https://rugcheck.xyz/tokens/Ah6KcTtLqrwxQwDQVAUYxKzb4yQJroDo1RrYwqYF4Lb9" class="hover-underline"><strong>RUGCHECKER</strong></a></div>
        <div><a href="https://twitter.com/cn_solana" class="hover-underline"><strong>TWITTER</strong></a></div>
        <div><a href="https://t.me/CN_Sol" class="hover-underline"><strong>TELEGRAM</strong></a></div>
      </div>
      <div class="flex bg-gray-300 px-3 py-1">
        <div class="pr-3">SEARCH</div>
        <input type="text" class="border outline-none" placeholder="  Vibes and Cartoon" />
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
          <div class="border"><img src="@/assets/cn-black.png" class="w-full h-28" /></div>
        </div>
        <div class="flex flex-col text-sm">
          <div> > <a class="hover-underline">PRIVACY POLICY</a></div>
          <div class="flex gap-1.5 flex-wrap">
            <div>> <a class="hover-underline">TRADEMARK INFORMATION</a></div>
            <div>> <a class="hover-underline">TERMS OF USE</a></div>
            <div>> <a class="hover-underline">PARENT GUIDE</a></div>
            <div>> <a class="hover-underline">TV PARENTAL GUIDELINES</a></div>
          </div>
          <div> @2023 $CN Token. We Are Not Affiliated With The Official Cartoon Network</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.hover-underline:hover {
  text-decoration: underline;
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
