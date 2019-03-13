<template>
    <div id="app">
        <v-app dark>
            <course-viewer v-bind:input="data"></course-viewer>
        </v-app>
    </div>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import {
        VBtn,
        VCard,
        VDivider,
        VIcon,
        VList,
        VListTile,
        VListTileAction,
        VListTileAvatar,
        VListTileContent,
        VListTileTitle,
        VNavigationDrawer,
        VToolbar
    } from 'vuetify/lib';
    import CourseViewer from '@/components/CourseViewer.vue';

    @Component({
        components: {
            CourseViewer,
        },
    })
    export default class App extends Vue {


        public data = {
            activeId: 'start',
            categories: [
                {
                    name: 'Observable basics',
                    lectures: [
                        {
                            id: 'build-your-own-observable',
                            name: 'Build our own Observable',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'what-is-an-operator-diagram',
                        },
                        {
                            id: 'what-is-an-operator-diagram',
                            name: 'What is an operator (diagram)',
                            url: 'https://youtube.com/embed/AUlo_7U-Sog?autoplay=1',
                            time: '5:21',
                        },
                        {
                            id: 'what-is-an-operator-code',
                            name: 'What is an operator (code)',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'passing-data-to-an-operator'
                        },
                        {
                            id: 'passing-data-to-an-operator',
                            name: 'Passing data to an operator',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'map'
                        },
                    ],
                },
                {
                    name: 'Operators',
                    lectures: [
                        {
                            id: 'map',
                            name: 'Map',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'filter',
                        },
                        {
                            id: 'filter',
                            name: 'Filter',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'reduce',
                        },
                        {
                            id: 'reduce',
                            name: 'Reduce',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'scan',
                        },
                        {
                            id: 'scan',
                            name: 'Scan',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'take',
                        },
                        {
                            id: 'take',
                            name: 'Take',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'tap',
                        },
                        {
                            id: 'tap',
                            name: 'Tap',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'takeUntil',
                        },
                        {
                            id: 'takeUntil',
                            name: 'TakeUntil',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'debounceTime',
                        },
                        {
                            id: 'debounceTime',
                            name: 'DebounceTime',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'mergeMap',
                        },
                        {
                            id: 'mergeMap',
                            name: 'MergeMap',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'mergeMap',
                        },
                        {
                            id: 'switchMap',
                            name: 'SwitchMap',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'concatMap',
                        },
                        {
                            id: 'concatMap',
                            name: 'ConcatMap',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'interval',
                        },
                    ],
                },
                {
                    name: 'Static Operators',
                    lectures: [
                        {
                            id: 'interval',
                            name: 'Interval',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'timer',
                        },
                        {
                            id: 'timer',
                            name: 'Timer',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'of',
                        },
                        {
                            id: 'of',
                            name: 'Of',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'merge',
                        },
                        {
                            id: 'merge',
                            name: 'Merge',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                            next: 'combineLatest'
                        },
                        {
                            id: 'combineLatest',
                            name: 'CombineLatest',
                            url: 'https://www.youtube.com/embed/kLzseIElKjU?autoplay=1',
                            time: '5:21',
                        },
                    ],
                }
            ],
        };
    }
</script>

<style>
.time-icon {
    font-size: 16px;
    margin-right: 5px;
}
</style>
