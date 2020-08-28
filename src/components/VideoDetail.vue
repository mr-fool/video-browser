<template>
    <div v-html=video.snippet.title>
        
    </div>   
</template>

<script>
export default {
    name: 'VideoDetail',
    props: ['video']
}
</script>