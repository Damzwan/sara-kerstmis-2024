<script setup lang="ts">
import { ref, watch, onMounted } from "vue";
import pc from "@/assets/pc.png";
import xp from "@/assets/xp.png";
import camera from "@/assets/camera.png";
import blood from "@/assets/bloodsplatter.png";
import sara from "@/assets/sara.png";
import ms from "@/assets/ms.png";
import folder from "@/assets/folder.png";
import lowresbg from "@/assets/lowresbackground.jpg";
import lrgebouw from "@/assets/liedekerkegebouw.jpg";
import lr1 from "@/assets/lr1.jpg";
import lr2 from "@/assets/lr2.jpg";
import lr3 from "@/assets/lr3.jpg";
import lr4 from "@/assets/lr4.jpg";
import gunny from "@/assets/gun.png";
import lr5 from "@/assets/lr5.jpg";
import startupSound from "@/assets/startup.mp3";
import doom from "@/assets/doom.mp3";
import gun from "@/assets/gun.mp3";
import childhood from "@/assets/childhood.mp3";
import industrial from "@/assets/industrial.mp3";

import childhood1 from "@/assets/childhood/1.jpg";
import childhood2 from "@/assets/childhood/2.jpg";
import childhood3 from "@/assets/childhood/3.jpg";
import childhood4 from "@/assets/childhood/4.jpg";
import childhood5 from "@/assets/childhood/5.jpg";
import childhood6 from "@/assets/childhood/6.jpg";
import childhood7 from "@/assets/childhood/7.jpg";
import childhood8 from "@/assets/childhood/8.jpg";
import childhood9 from "@/assets/childhood/9.jpg";

import italy1 from "@/assets/italy/1.jpg";
import italy2 from "@/assets/italy/2.jpg";
import italy3 from "@/assets/italy/3.jpg";
import italy4 from "@/assets/italy/4.jpg";
import italy5 from "@/assets/italy/5.jpg";
import italy6 from "@/assets/italy/6.jpg";
import italy7 from "@/assets/italy/7.jpg";

import thailand1 from "@/assets/thailand/1.jpeg";
import thailand2 from "@/assets/thailand/2.jpeg";
import thailand3 from "@/assets/thailand/3.jpeg";
import thailand4 from "@/assets/thailand/4.jpeg";
import thailand5 from "@/assets/thailand/5.jpeg";
import thailand6 from "@/assets/thailand/6.jpeg";

import primary1 from "@/assets/primary/1.jpeg";

import highschool1 from "@/assets/highschool/1.jpg";
import highschool2 from "@/assets/highschool/2.jpg";
import highschool3 from "@/assets/highschool/3.jpg";
import highschool4 from "@/assets/highschool/4.jpg";
import highschool5 from "@/assets/highschool/5.jpg";
import highschool6 from "@/assets/highschool/6.jpg";
import highschool7 from "@/assets/highschool/7.jpg";

import university1 from "@/assets/university/1.jpg";
import university2 from "@/assets/university/2.jpg";
import university3 from "@/assets/university/3.jpg";
import university4 from "@/assets/university/4.jpg";
import university5 from "@/assets/university/5.jpg";

import computer from "@/assets/desktop/computer.png";
import network from "@/assets/desktop/network.png";
import document from "@/assets/desktop/documents.png";
import notepad from "@/assets/desktop/notepad.png";
import logo from "@/assets/desktop/logo.svg";

import highschoolMusic from "@/assets/music/highschool.mp3";
import italyMusic from "@/assets/music/italy.mp3";
import thailandMusic from "@/assets/music/thailand.mp3";
import universityMusic from "@/assets/music/university.mp3";
import primaryMusic from "@/assets/music/primary.mp3";
import futureMusic from "@/assets/music/future.mp3";



import Typed from 'typed.js';

// Reactive variable for zoom state
const isZoomed = ref(false);
const startupFinished = ref(false)
const isChildHoodOpen = ref(false)
const childhoodImages = ref([
  childhood1,
  childhood2,
  childhood3,
  childhood4,
  childhood5,
  childhood6,
  childhood7,
  childhood8,
  childhood9,
]);
const childhoodContainer = ref(null);
let scrollInterval = null;

const isMineSweeperOpen = ref(false)
const isMemoryGameOpen = ref(false)
const isPrimaryOpen = ref(false)
const isHighSchoolOpen = ref(false)
const isUniversityOpen = ref(false)
const isItalyOpen = ref(false)
const isThailandOpen = ref(false)
const isFutureOpen = ref(false)

const childhoodAudio = new Audio(childhood)
const industrialAUdio = new Audio(industrial)
const doomAudio = new Audio(doom)
const gunAudio = new Audio(gun)

const primaryAudio = new Audio(primaryMusic)
const highschoolAudio = new Audio(highschoolMusic)
const universityAudio = new Audio(universityMusic)
const italyAudio = new Audio(italyMusic)
const thailandAudio = new Audio(thailandMusic)
const futureAudio = new Audio(futureMusic)


const bloodVisible = ref({})

watch(isMineSweeperOpen, () => {
  isMineSweeperOpen.value ? doomAudio.play() : doomAudio.pause();
})

watch(isChildHoodOpen, () => {
  if (isChildHoodOpen.value) startScrolling()
  isChildHoodOpen.value ? childhoodAudio.play() : childhoodAudio.pause();
})

watch(isMemoryGameOpen, () => {
  isMemoryGameOpen.value ? industrialAUdio.play() : industrialAUdio.pause();
})

watch(isPrimaryOpen, () => {
  isPrimaryOpen.value ? primaryAudio.play() : primaryAudio.pause();
  new Typed('#primaryText', {
    strings: ['I was always following you around thinking you were the coolest person in this world. Even though you probably thought I was just a nuisance. I was constantly chasing you and your friends everywhere. Started doing all the same hobbies as you like judo and gymnastics - probably our parents didnt even want to drive us to all these different places anymore. And then I even went to the same summer camp as you'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

watch(isHighSchoolOpen, () => {
  isHighSchoolOpen.value ? highschoolAudio.play() : highschoolAudio.pause();
  new Typed('#highschoolText', {
    strings: ['First part of highschool we were drifting apart from each other for the first time ever. You were going through such a rough time and it was really painful to watch. We would talk from time to time but you needed your space and I understood that. I still thought you were the coolest sister ever though, even while I started minding my own business. Then after your traffic accident we became close again... the thought of losing you was just unbearable and it was the last thing I wanted in the world. We started going out eating sushi together, went to plaja moderna together in constanta, shared all our struggles with each other. I remember barging into your room every single evening just to talk with you or say something stupid. Even started coming to sleep over in your room even though we literally lived right next to each other'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

watch(isUniversityOpen, () => {
  isUniversityOpen.value ? universityAudio.play() : universityAudio.pause();
  new Typed('#universityText', {
    strings: ['When you left for Brussels it was just heartbreaking to live like that. All alone in our home... it took me such a long time to adjust to it. We would still see each other of course and I dont blame you at all - you needed your space to discover yourself in this new environment. We still managed to go on some really nice holidays together like that time in Turkey. Remember when we wanted to go to those waterfalls and had to take the bus? That random guy just took our money and disappeared for like half an hour with our cards'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

watch(isItalyOpen, () => {
  isItalyOpen.value ? italyAudio.play() : italyAudio.pause();
  new Typed('#italyText', {
    strings: ['At first in Italy we were separated but I was just so excited when your erasmus to Peru got cancelled (sorry not sorry) and you ended up coming to live basically right next to me. Those months were honestly one of the best of my life and you had such a huge part in that. I loved that we traveled together and that you would stay over at my place in milan to play poker together and judge my roomies. It really felt like we were never closer than that. Even after Italy when we didnt see each other that much it still felt like our bond was as strong as ever. I loved our magical experience in Amsterdam and everything that came after. It felt like finally we started talking about things we never talked about before - our past love everything. It was really what kept me going before my trip - just us hanging together watching movies and talking about life. It wasnt very frequent but every single time was just a godsent'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

watch(isThailandOpen, () => {
  isThailandOpen.value ? thailandAudio.play() : thailandAudio.pause();
  new Typed('#thailandText', {
    strings: ['I am just so grateful for you coming all the way to Thailand to see me and return together. I was so anxious during those days, completely unsure of my future and everything else. You helped me pass those days with ease, helped me appreciate the country way more and made my return so much smoother. It was like you were this pillow that cushioned the fall for me coming back. Even though we only spent 2 weeks together it felt like there was still so much more we needed to talk about'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

watch(isFutureOpen, () => {
  isFutureOpen.value ? futureAudio.play() : futureAudio.pause();
  new Typed('#futureText', {
    strings: ['So much has happened... I really wish I had more time to write it all down but my time is literally running out right now. One thing that most people envy about us is that our bond is just so strong. Its something that Ive always appreciated and always will. Its something we should maintain no matter the time age or distance between us. And Im sure we will. You might be going through the roughest time of your life right now and it might feel like there is no one that truly can understand what youre going through. That might be the case, it might not be. But if we dont talk to us and make us understand... Just please accept the help you deserve. You mean absolutely everything to me, I would not have survived so far without you. No matter what the future brings well face it together. Merry Christmas Sara'],
    typeSpeed: 50,
    cursorChar: '❤️'
  });
});

// Function to toggle zoom state
const toggleZoom = () => {
  isZoomed.value = !isZoomed.value;
  setTimeout(() => {
    startupFinished.value = true
    const audio = new Audio(startupSound)
    audio.play()
  }, 2000)
};

const shoot = (targetId) => {
  gunAudio.pause();
  gunAudio.currentTime = 0;
  gunAudio.play(); // Play the gun sound
  bloodVisible.value[targetId] = true; // Make blood visible for the shot target
};

const startScrolling = () => {
  const container = childhoodContainer.value;
  if (!container) return;

  const scrollStep = 1; // Pixels to scroll per interval
  const interval = 60; // Milliseconds between scrolls

  const scroll = () => {
    // Check if the container can scroll
    if (container.clientHeight + container.scrollTop < container.scrollHeight) {
      container.scrollTop += scrollStep; // Increment scroll position
    } else {
      clearInterval(scrollInterval); // Stop the interval if no scrolling is possible
      new Typed('#childhoodText', {
        strings: ['I do not remember too much from back then. We were always together though... eating cornflakes outside while exploring that playgarden in front of our home. I remember throwing a tennisbal in your face and getting punished by being stuck in the corner for hours. And then there were those times we used to annoy the neighbor by dropping maple helicopters from the balcony'],
        typeSpeed: 50,
        cursorChar: '❤️'
      });
    }
  };

  // Set the scrolling interval
  scrollInterval = setInterval(scroll, interval);
};

const getRandomStyle = () => {
  const randomRotation = Math.random() * 20 - 10; // Rotation between -10 and 10 degrees
  const randomX = Math.random() * 30 - 15; // Translation X (-15px to 15px)
  const randomY = Math.random() * 30 - 15; // Translation Y (-15px to 15px)

  return {
    transform: `rotate(${randomRotation}deg) translate(${randomX}px, ${randomY}px)`,
    transition: 'transform 0.5s ease',
  };
};

const cards = ref([])
const flipped = ref([])
const matched = ref([])
const isMaximized = ref(false)

onMounted(() => {
  const cardPairs = [
    { id: 1, img: childhood1 },
    { id: 2, img: childhood2 },
    { id: 3, img: childhood3 },
    { id: 4, img: childhood4 },
    { id: 5, img: childhood5 }
  ]

  cards.value = [...cardPairs, ...cardPairs]
    .sort(() => Math.random() - 0.5)
    .map((card, index) => ({ ...card, uniqueId: index }))
})

const handleClick = (uniqueId) => {
  if (flipped.value.length === 2) return
  if (flipped.value.includes(uniqueId) || matched.value.includes(uniqueId)) return

  flipped.value.push(uniqueId)

  if (flipped.value.length === 2) {
    const [first, second] = flipped.value
    const firstCard = cards.value.find(card => card.uniqueId === first)
    const secondCard = cards.value.find(card => card.uniqueId === second)

    if (firstCard.id === secondCard.id) {
      matched.value.push(first, second)
    }

    setTimeout(() => {
      flipped.value = []
    }, 1000)
  }
}
</script>

<template>
  <main class="w-screen h-screen bg-black flex justify-center items-center">
    <!-- Zoom Container -->
    <div class="relative overflow-hidden transition-transform duration-700"
      :class="{ 'scale-[3.2] translate-y-[71%]': isZoomed }">
      <!-- Background Image -->
      <img :src="pc" alt="" class="w-full h-auto object-cover bg-img" />

      <!-- Zoom Button -->
      <div class="absolute left-[805px] bg-blue-700 z-10 top-[348px] w-7 h-7 cursor-pointer" @click="toggleZoom"></div>

      <div class="absolute left-[300px] top-[100px] z-10">
      </div>

      <!-- Overlay -->
      <div class="absolute w-[398px] h-[235px] left-[470px] top-[95px] rounded-2xl flex justify-center items-center"
        style="clip-path: polygon(0% 0%, 100% 0%, 96% 99%, 4% 99%);"
        :class="{ 'bg-blue-700': isZoomed && !startupFinished }">

        <div v-show="isZoomed && !startupFinished" class="flex flex-col justify-center items-center space-y-4">
          <img :src="xp" alt="" width="200px" height="200px">
          <progress></progress>
        </div>

        <div v-show="isZoomed && startupFinished" class="flex justify-center items-center w-full h-full">
          <img :src="lowresbg" alt="" class="object-cover rounded-2xl absolute">

          <div class="taskbar">
            <div class="start-button"><img :src="logo"> start</div>

            <div class="opened-tabs">
              <div class="open-tab" onclick="window.open('https://faisalakhtar.github.io/')"><img :src="document">Magic
                Fungi Research</div>
              <div class="open-tab" onclick="window.open('https://github.com/faisalAkhtar/')"><img :src="computer"> My
                Computer</div>
              <div class="open-tab" onclick="window.open('https://twitter.com/faisallakhtarr/')"><img :src="network"> My
                Network</div>
              <div class="open-tab readme active"><img :src="notepad"> ReadME.txt</div>
            </div>

            <div class="time">11:20 PM</div>
          </div>

          <div class="absolute z-20 left-2 top-2 flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isChildHoodOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Early years</p>
          </div>

          <div class="absolute z-20 left-2 top-12 flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isPrimaryOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Primary school</p>
          </div>

          <div class="absolute z-20 left-2 top-[5.5rem] flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isHighSchoolOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Highschool</p>
          </div>

          <div class="absolute z-20 left-2 top-[8rem] flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isUniversityOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">University</p>
          </div>

          <div class="absolute z-20 left-12 top-12 flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isItalyOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Italy</p>
          </div>

          <div class="absolute z-20 left-12 top-2 flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isThailandOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Thailand</p>
          </div>

          <div class="absolute z-20 left-[5.5rem] top-2 flex flex-col justify-center items-center w-10 cursor-pointer"
            @click="isFutureOpen = true">
            <img :src="folder" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Future</p>
          </div>


          <div class="absolute z-20 right-2 top-2 flex flex-col justify-center items-center w-20 cursor-pointer"
            @click="isMineSweeperOpen = true">
            <img :src="ms" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Liedekerke Sweeper</p>
          </div>

          <div class="absolute z-20 right-2 top-12 flex flex-col justify-center items-center w-20 cursor-pointer"
            @click="isMemoryGameOpen = true">
            <img :src="ms" alt="" width="24">
            <p class="text-white text-[5px] -mt-0.5 vt323-regular">Poor Memory Improver</p>
          </div>

          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isChildHoodOpen" ref="childhoodContainer">
            <div class="title-bar">
              <div class="title-bar-text">Childhood Memories</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isChildHoodOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-4 justify-items-center items-start">
              <div v-for="(image, index) in childhoodImages" :key="index" :style="getRandomStyle()" class="relative">
                <img :src="image" alt="" class="block" width="150" />
              </div>
              <div class="col-span-2 flex flex-col items-center">
                <p class="text-[8px] vt323-regular" id="childhoodText"></p>
                <button @click="isChildHoodOpen = false">Done</button>
              </div>
            </div>

          </div>

          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isPrimaryOpen">
            <div class="title-bar">
              <div class="title-bar-text">Primary School</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isPrimaryOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-8">
              <div class="grid grid-cols-2 gap-2">
                <img :src="primary1" width="1000" :style="getRandomStyle()" alt="">
              </div>

              <div>
                <p id="primaryText" class="vt323-regular"></p>
              </div>
            </div>
          </div>


          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isHighSchoolOpen">
            <div class="title-bar">
              <div class="title-bar-text">HighSchool</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isHighSchoolOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-8">

              <div>
                <p id="highschoolText" class="vt323-regular"></p>
              </div>

              <div class="grid grid-cols-2 gap-2">
                <img :src="highschool1" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool2" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool3" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool4" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool5" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool6" width="1000" :style="getRandomStyle()" alt="">
                <img :src="highschool7" width="1000" :style="getRandomStyle()" alt="">
              </div>

            </div>
          </div>

          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isUniversityOpen">
            <div class="title-bar">
              <div class="title-bar-text">University</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isUniversityOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-8">
              <div class="grid grid-cols-1 gap-2">
                <img :src="university1" width="1000" :style="getRandomStyle()" alt="">
                <img :src="university2" width="1000" :style="getRandomStyle()" alt="">
                <img :src="university3" width="1000" :style="getRandomStyle()" alt="">
                <img :src="university4" width="1000" :style="getRandomStyle()" alt="">
                <img :src="university5" width="1000" :style="getRandomStyle()" alt="">
              </div>

              <div>
                <p id="universityText" class="vt323-regular"></p>
              </div>
            </div>
          </div>

          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isItalyOpen">
            <div class="title-bar">
              <div class="title-bar-text">Italy</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isItalyOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-8">

              <div>
                <p id="italyText" class="vt323-regular"></p>
              </div>

              <div class="grid grid-cols-2 gap-2">
                <img :src="italy1" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy2" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy3" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy4" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy5" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy6" width="1000" :style="getRandomStyle()" alt="">
                <img :src="italy7" width="1000" :style="getRandomStyle()" alt="">
              </div>

            </div>
          </div>


          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isThailandOpen">
            <div class="title-bar">
              <div class="title-bar-text">Thailand</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isThailandOpen = false"></button>
              </div>
            </div>

            <div class="window-body grid grid-cols-2 gap-8">
              <div class="grid grid-cols-2 gap-2">
                <img :src="thailand1" width="1000" :style="getRandomStyle()" alt="">
                <img :src="thailand2" width="1000" :style="getRandomStyle()" alt="">
                <img :src="thailand3" width="1000" :style="getRandomStyle()" alt="">
                <img :src="thailand4" width="1000" :style="getRandomStyle()" alt="">
                <img :src="thailand5" width="1000" :style="getRandomStyle()" alt="">
                <img :src="thailand6" width="1000" :style="getRandomStyle()" alt="">
              </div>
              <div>
                <p id="thailandText" class="vt323-regular"></p>
              </div>
            </div>
          </div>

          <div class="w-11/12 h-[95%] z-20 window overflow-scroll" v-show="isFutureOpen">
            <div class="title-bar">
              <div class="title-bar-text">Future</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isFutureOpen = false"></button>
              </div>
            </div>

            <div class="window-body">

              <div>
                <p id="futureText" class="vt323-regular"></p>
              </div>


            </div>
          </div>


          <div class="w-11/12 h-[95%] z-20 window" v-if="isMineSweeperOpen">
            <div class="title-bar">
              <div class="title-bar-text">Liedekerke Sweeper</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isMineSweeperOpen = false"></button>
              </div>
            </div>

            <div class="window-body flex space-x-3 relative">
              <div>
                <img :src="lrgebouw" alt="" width="180">
                <img :src="sara" alt="" width="80" class="absolute -bottom-1 -left-5">
                <img :src="gunny" alt="" width="60" class="absolute bottom-8 left-3 -rotate-12">
                <div class="absolute left-[40px] top-[20px] cursor-pointer" @click="shoot(1)">
                  <img :src="lr1" alt="" width="30">
                  <img v-if="bloodVisible[1]" :src="blood" alt="" width="30" class="z-40 -mt-7">
                </div>

                <img :src="lr2" alt="" width="30" class="absolute left-[80px] top-[10px] cursor-pointer"
                  @click="shoot(2)">
                <img v-if="bloodVisible[2]" :src="blood" alt="" width="30" class="absolute left-[80px] top-[10px] z-40">

                <img :src="lr3" alt="" width="30" class="absolute left-[20px] top-[70px] cursor-pointer"
                  @click="shoot(3)">
                <img v-if="bloodVisible[3]" :src="blood" alt="" width="30" class="absolute left-[20px] top-[70px] z-40">

                <img :src="lr4" alt="" width="30" class="absolute left-[100px] top-[80px] cursor-pointer"
                  @click="shoot(4)">
                <img v-if="bloodVisible[4]" :src="blood" alt="" width="30" class="absolute left-[100px] top-[80px] z-40">

                <img :src="lr5" alt="" width="30" class="absolute left-[140px] top-[40px] cursor-pointer"
                  @click="shoot(5)">
                <img v-if="bloodVisible[5]" :src="blood" alt="" width="30" class="absolute left-[140px] top-[40px] z-40">
              </div>
              <div>
                <p class="text-lg text-red-600 vt323-regular">Destroy Liedekerke</p>
                <p class="text-md text-green-700 vt323-regular">Main Objective: Kill all lawyers</p>
                <p class="text-md text-purple-600 vt323-regular">Side quest: Bomb the building</p>
              </div>
            </div>

          </div>

          <div class="w-11/12 h-[95%] z-20 window" v-if="isMemoryGameOpen">
            <div class="title-bar">
              <div class="title-bar-text">Poor Memory Improver</div>
              <div class="title-bar-controls">
                <button aria-label="Close" @click="isMemoryGameOpen = false"></button>
              </div>
            </div>

            <div class="window-body flex space-x-3 relative">
              <div class="p-4 w-full h-full">
                <div class="grid grid-cols-5 gap-2">
                  <div v-for="card in cards" :key="card.uniqueId"
                    class="aspect-square cursor-pointer transform transition-transform hover:scale-105"
                    @click="handleClick(card.uniqueId)">
                    <div :class="[
                      'w-full h-full border-2 border-gray-300 rounded',
                      flipped.includes(card.uniqueId) || matched.includes(card.uniqueId)
                        ? 'bg-white'
                        : 'bg-blue-500'
                    ]">
                      <img v-if="flipped.includes(card.uniqueId) || matched.includes(card.uniqueId)" :src="card.img"
                        :alt="'Card ' + card.id" class="w-full h-full object-cover rounded" />
                    </div>
                  </div>
                </div>
              </div>
            </div>

          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
body,
html {
  overflow: hidden;
}

/* Ensure the image stays responsive */
.bg-img {
  width: 100%;
  height: auto;
  object-fit: cover;
  transform-origin: center;
}

.taskbar {
  background-color: #245EDC;
  background: linear-gradient(to bottom, #245EDC 0%, #3f8cf3 9%, #245EDC 18%, #245EDC 92%, #1941A5 100%) center/cover no-repeat;
  position: absolute;
  bottom: 1px;
  left: 12px;
  width: 94%;
  height: 10px;
  /* 32px / 3.2 */
}

.start-button {
  height: 100%;
  float: left;
  font-size: 7px;
  /* 22px / 3.2 */
  line-height: 7px;
  font-weight: bold;
  font-style: italic;
  background: radial-gradient(circle, #5eac56 0%, #3c873c 100%) center/cover no-repeat;
  box-shadow: 0px 2px 3px #79ce71 inset, 1px 0 2px #3f8cf3;
  padding: 1px 8px 2px 3px;
  text-shadow: 0.3px 0.3px 1px #222;
  border-radius: 0px 2.5px 2.5px 0px;
  margin-right: 5px;
  cursor: pointer;
}

.start-button img {
  height: 6px;
  /* 20px / 3.2 */
  filter: drop-shadow(0.3px 0.3px 0.3px #222);
  transform: translateY(1px);
}

.opened-tabs {
  width: calc(100% - 70px);
  /* 225px / 3.2 */
  float: left;
}

.open-tab {
  width: 47px;
  /* 150px / 3.2 */
  height: 8px;
  /* 26px / 3.2 */
  margin: 1px 0;
  float: left;
  background-color: #4892F7;
  background: url(btn1) no-repeat 0 0;
  border: 0.3px solid #306FD9;
  border-radius: 1px;
  font-family: calibri, monospace;
  font-size: 4.5px;
  /* 14px / 3.2 */
  line-height: 4.5px;
  padding: 2.5px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
  word-wrap: break-word;
  cursor: pointer;
}

.open-tab img {
  height: 5.5px;
  /* 18px / 3.2 */
  float: left;
  transform: translateY(-1px);
  margin-right: 1.5px;
}

.time {
  height: 100%;
  float: right;
  font-family: calibri, monospace;
  font-size: 4.5px;
  /* 14px / 3.2 */
  line-height: 4.5px;
  background: linear-gradient(to bottom, #1290E9 0%, #19B9F3 9%, #1290E9 18%, #1290E9 92%, #1941A5 100%) center/cover no-repeat;
  box-shadow: 0px 2px 3px #14A5F0 inset, 0px 2px 3px #333333;
  padding: 3px 5px 3px 8px;
  border-left: 0.3px solid #092E51;
  text-shadow: 0.3px 0.3px 0.6px #222;
  cursor: pointer;
  text-transform: uppercase;
}

.vt323-regular {
  font-family: "VT323", serif;
  font-weight: 400;
  font-style: normal;
}
</style>
