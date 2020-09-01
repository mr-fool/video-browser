<template>
    <div v-if="video">
            <div class="details">
                <h4 v-html=video.snippet.title> </h4>
                <p v-html=video.snippet.description></p>
            </div>
    </div>   
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['video']
}
</script>