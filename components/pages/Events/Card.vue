<template>
    <div class="event eventItem" :class="props.extraClass" @click="emits('selected')">
        <div class="eventItem-preview">
            <NuxtLink data-bs-target="#events" data-bs-toggle="modal">
                <img :data-src="imageUrl" v-lazy-load :key="props.item.id" alt="">
            </NuxtLink>
        </div>
        <div class="eventItem-content">
            <h4>
                <NuxtLink>{{ props.item.title.rendered }}</NuxtLink>
            </h4>
            <NuxtLink data-bs-target="#events" class="btn btn-primary" data-bs-toggle="modal">
                Подробнее
                <svg xmlns="http://www.w3.org/2000/svg" width="25" height="24" viewBox="0 0 25 24" fill="#121212">
                    <g mask="url(#mask0_472_218)">
                        <path
                            d="M17.1116 12.7498H5.75C5.53718 12.7498 5.35898 12.678 5.2154 12.5345C5.0718 12.3909 5 12.2127 5 11.9999C5 11.787 5.0718 11.6088 5.2154 11.4653C5.35898 11.3217 5.53718 11.2499 5.75 11.2499H17.1116L13.8192 7.95753C13.6705 7.80882 13.5971 7.63478 13.599 7.43543C13.6009 7.23608 13.6743 7.05884 13.8192 6.90371C13.9743 6.74859 14.1525 6.66847 14.3538 6.66333C14.5551 6.6582 14.7333 6.7332 14.8884 6.88833L19.3672 11.3672C19.4608 11.4608 19.5269 11.5595 19.5653 11.6633C19.6038 11.7672 19.623 11.8793 19.623 11.9999C19.623 12.1204 19.6038 12.2325 19.5653 12.3364C19.5269 12.4402 19.4608 12.5389 19.3672 12.6325L14.8884 17.1114C14.7397 17.2601 14.5631 17.3335 14.3586 17.3316C14.1541 17.3296 13.9743 17.2511 13.8192 17.096C13.6743 16.9409 13.5993 16.7652 13.5942 16.5691C13.5891 16.3729 13.6641 16.1973 13.8192 16.0422L17.1116 12.7498Z" />
                    </g>
                </svg>
            </NuxtLink>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    item: {
        type: Object,
        default: {}
    },
    extraClass : {
        type: String,
        default: ''
    }
})

const emits = defineEmits(['selected'])

const imageUrl = computed(() => props.item?.jetpack_featured_media_url || '')
</script>