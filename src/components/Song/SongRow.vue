<template>
    <div class="song-row">
        <div class="song-list">
            <slot name="song-list"></slot>
        </div>
        <div class="noresults">
        </div>
        <div class="pagination" v-if="!noactions">
            <slot name="controls"></slot>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'SongRow',
        props: [
            'title',
            'noactions'
        ]
    }
</script>

<style scoped lang="less">
    .song-row {
        display: grid;
        grid-template-rows: auto 1fr;
        grid-gap: 5px;
        
        & .song-list {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
            grid-gap: 15px;
        }
        & .song-list-noresults {
            display: none;
            background: rgba(255,255,255,0.1);
            border-radius: 6px;
            padding: 25px;
            opacity: 0.6;
            text-align: center;

            &.active {
                display: block;
            }
        }
        & .pagination {
            text-align: right;
            margin-top: 25px;

            & .button {
                margin-left: 10px;
                display: inline;
            }
        }
    }
</style>
