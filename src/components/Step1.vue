<template>
    <div>
        <h6 class="font-weight-medium body-1">1. Select a Paper Size</h6>
        
        <v-slide-group class="lighten-1 grey py-7 px-4 mb-6">
            <v-slide-item v-for="(value, index) in paper_sizes" :key="index">
                <div class="mx-4 mb-1">
                    <v-card :class="{'white--text' : selected_size.paper === value.size}" :color="selected_size.paper === value.size ? 'primary' : ''" :height="value.height" :width="value.width" @click="selected_size.paper = value.size" class="justify-center align-center d-flex">
                        <h2 class="font-weight-medium">{{ value.size }}</h2>
                    </v-card>
                </div>
            </v-slide-item>
        </v-slide-group>
    </div>
</template>

<script>
export default {
    props: ['selected_size'],

    data() {
        return {
            paper_sizes: [
                { size: '4R', height: '150', width: '100' },
                { size: '5R', height: '160', width: '125' }
            ]
        }
    }
}
</script>