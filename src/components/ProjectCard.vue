<script setup>
const props = defineProps({
  project: {
    type: Object,
    required: true,
  },
});
function sendToLink() {
  window.open(props.project.link, "_blank");
}
</script>
<template>
    <div
        class="group  bg-p-lightBlackisBrown font-bold cursor-pointer"
        @click="sendToLink"
    >
        <div class="p-2 group-hover:border-2 group-active:scale-95 transition-all duration-300 group-hover:border-p-lightRed">
            <img
                :src="  project.image || '/src/assets/MainPersonalPhoto.jpg'"
                alt="Project Image"
                class="w-full h-auto object-cover transition-all duration-300 "
            />
        </div>
        <div class="flex flex-col justify-between p-2">
            <h3 class="text-xl text-p-green font-bold">{{ project.title }}</h3>
            <div class="flex justify-between">
                <p class="text-sm font-light text-justify text-p-lightBrown">{{ project.description }}</p>
            </div>
        </div>
    </div>
</template>