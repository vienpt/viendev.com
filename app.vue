<script setup lang="ts">
import { ref, watch } from "vue";
import resume from "@/public/vienpham-resume.pdf";

const isShowDetail = ref(false);

function showInfoDetail() {
    isShowDetail.value = !isShowDetail.value;
}

watch(
    () => isShowDetail.value,
    () => {
        setTimeout(() => (isShowDetail.value = false), 10000);
    },
);
</script>

<template>
    <div class="flex justify-center items-center h-screen mx-auto">
        <div class="flex w-[425px] border border-black rounded-md p-5">
            <div class="flex gap-4 justify-center items-center">
                <NuxtImg
                    class="rounded-full"
                    width="100"
                    height="100"
                    src="https://github.com/vienpt.png"
                    alt="@vienpt"
                />
                <div class="w-full gap-2.5 flex flex-col">
                    <h2 class="font-bold text-xl">Vien Pham</h2>
                    <div class="leading-5 gap-2 flex">
                        <span>Tech enthusiast. Loves coding.</span>
                        <button @click="showInfoDetail">
                            <Icon
                                name="uil:info-circle"
                                style="color: black"
                                size="20"
                            />
                        </button>
                    </div>
                    <div class="space-x-1">
                        <NuxtLink
                            target="_blank"
                            to="https://github.com/vienpt"
                        >
                            <Icon
                                name="uil:github"
                                style="color: black"
                                size="24"
                            />
                        </NuxtLink>
                        <NuxtLink
                            target="_blank"
                            to="https://www.linkedin.com/in/vien-pham-887255a1/"
                        >
                            <Icon
                                name="uil:linkedin"
                                style="color: black"
                                size="24"
                            />
                        </NuxtLink>
                        <a target="_blank" :href="resume">
                            <Icon
                                name="uil:file-alt"
                                style="color: black"
                                size="24"
                            />
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div v-if="isShowDetail">
        <div
            class="absolute w-[425px] border rounded-md border-neutral-100 left-1/2 top-2/3 -translate-x-1/2 -translate-y-1/2 p-4 bg-neutral-300/10"
        >
            <div class="text-sm tracking-wide select-none">
                Always excited about new tech. Enjoys writing code and solving
                problems. Constantly learning and exploring new tools and
                languages.
            </div>
        </div>
    </div>
</template>

<style>
.dark-mode body {
    background-color: #f1e7d0;
    color: #433422;
}
</style>
