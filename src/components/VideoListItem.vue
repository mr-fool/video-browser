<template>
    <li class="list-group-item">
        <img :src="video.snippet.thumbnails.default.url" />
        <div v-html="video.snippet.title">
        </div>
    </li>

</template>

<script>
export default {
    name: 'VideoListItem',
    props: ['video']
}
</script>