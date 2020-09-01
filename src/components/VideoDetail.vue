<template>
    <div v-if="video">
        <h4>
            <div class="details" v-html=video.snippet.title>
                <p v-html=video.snippet.description></p>
            </div>
        </h4>
    </div>   
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['video']
}
</script>