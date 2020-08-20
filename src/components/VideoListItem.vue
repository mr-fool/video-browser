<template>
    <li class="list-group-item">
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