<template>
    <div class="button">
        <v-btn
            color="#E5E5E5"
            depressed
            height="100%"
            tile
        >
            <span><slot name="name"></slot></span>
            <v-icon class="mt-1 ml-1"><slot name="icon"></slot></v-icon> 
        </v-btn>
    </div>
</template>

<script>
export default {
    
}
</script>