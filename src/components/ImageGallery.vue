<script setup>
defineProps({
    isGrayspace: Boolean
})

const copyUrl = async (url) => {
    await navigator.clipboard.writeText(url);
}
</script>

<template>
    <v-card class="ma-5 pa-3">
        <v-row>
        <v-col
            v-for='n in 120'
            :key="n"
            cols="4"
            sm="3"
            md="2"
            lg="1"
        >
            <v-card v-on:click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${isGrayspace ? '&grayscale' : ''}`)">
                <v-img
                    :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${isGrayspace ? '&grayscale' : ''}`"
                    :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${isGrayspace ? '&grayscale' : ''}`"
                    aspect-ratio="1"
                    cover
                    class="bg-grey-lighten-2"
                >
                    <template v-slot:placeholder>
                        <v-row
                            class="fill-height ma-0"
                            align="center"
                            justify="center"
                        >
                            <v-progress-circular
                                indeterminate
                                color="grey-lighten-5"
                            ></v-progress-circular>
                        </v-row>
                    </template>
                </v-img>
            </v-card>
        </v-col>
    </v-row>
    </v-card>
</template>