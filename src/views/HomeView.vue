<script setup lang="ts">
import QrScanner from 'qr-scanner'
import { onMounted, ref } from 'vue'

const video = ref<HTMLVideoElement | null>(null)

const handleScan = (result: string) => {
  console.log(result)
}

onMounted(() => {
  // @ts-ignore
  const scanner = new QrScanner(video.value!, handleScan, {
    highlightScanRegion: true,
    highlightCodeOutline: true,
    aspectRatio: 1,
    calculateScanRegion: (video: HTMLVideoElement): any => {
      const width = video.videoWidth
      const height = video.videoHeight
      const size = Math.min(width, height) * 0.8
      const x = (width - size) / 2
      const y = (height - size) / 2
      return { x, y, width: size, height: size }
    }
  })
  scanner.start()
})
</script>

<template>
  <main class="p-3">
    <div class="flex flex-col gap-6">
      <img src="@/assets/logo.png" alt="logo" class="w-24 mx-auto" />
      <p class="text-3xl text-center font-bold">Scan the qr code</p>
      <div class="bg-white w-full aspect-square rounded-3xl shadow max-w-96 self-center">
        <video ref="video" class="h-full object-cover rounded-3xl"></video>
      </div>
      <div class="bg-white rounded-2xl px-3 py-3 flex flex-col gap-3 shadow">
        <div class="flex flex-row gap-3 content-center text-center font-medium">
          <div class="h-9 w-9 border rounded-xl content-center text-center border-emerald-200">1</div>
          <p class="self-center">Scan the qr code</p>
        </div>
        <div class="flex flex-row gap-3 content-center text-center font-medium">
          <div class="h-9 w-9 border rounded-xl content-center text-center border-emerald-200">2</div>
          <p class="self-center">Order your food</p>
        </div>
        <div class="flex flex-row gap-3 content-center text-center font-medium">
          <div class="h-9 w-9 border rounded-xl content-center text-center border-emerald-200">3</div>
          <p class="self-center">Enjoy your meal</p>
        </div>
      </div>
      <button class="transition-transform duration-300 transform active:scale-[102%] bg-white text-emerald-400 font-bold shadow
      border border-emerald-400 hover:bg-emerald-400 hover:text-white rounded-2xl py-2">
        Call waiter
      </button>
    </div>
  </main>
</template>
