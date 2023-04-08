<template>
    <div>
        <h6 class="font-weight-medium body-1">2. Select a Photo Size</h6>

        <v-slide-group class="lighten-1 grey py-7 px-4 mb-6">
            <v-slide-item v-for="(value, index) in photo_sizes" :key="index">
                <div class="mx-4 mb-1">
                    <v-card :class="{'white--text' : selected_size.photo === value.size}" :color="selected_size.photo === value.size ? 'primary' : ''" :height="value.height" :width="value.width" @click="selected_size.photo = value.size" class="justify-center align-center d-flex">
                        <div class="text-center">
                            <h2 class="font-weight-medium">{{ value.size }}</h2>
                            <span class="font-weight-medium">{{ value.description }}</span>
                        </div>
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
            photo_sizes: [
                { size: '1x1', height: '75', width: '150', description: '12 pcs. for ₱ 20' },
                { size: '2x2', height: '75', width: '150', description: '4 pcs. for ₱ 25' }
            ]
        }
    }
}
</script>