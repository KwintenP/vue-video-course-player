<template>
    <div id="app">
        <v-app dark>
            <course-viewer v-bind:input="data"></course-viewer>
        </v-app>
    </div>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import CourseViewer from '@/components/CourseViewer.vue';

    @Component({
        components: {
            CourseViewer,
        },
    })
    export default class App extends Vue {


        public data = {
            activeId: 'start',
            intro: {
                id: 'intro',
                name: 'Intro',
                url: 'https://www.youtube.com/embed/R9Goq6093hg?autoplay=1',
                time: '?:??',
                next: 'build-your-own-observable',
            },
            categories: [
                {
                    name: 'Observable basics',
                    lectures: [
                        {
                            id: 'build-your-own-observable',
                            name: 'Build our own Observable',
                            url: 'https://www.youtube.com/embed/2kg0ko38wTA?autoplay=1',
                            time: '5:37',
                            next: 'what-is-an-operator-diagram',
                        },
                        {
                            id: 'what-is-an-operator-diagram',
                            name: 'What is an operator (diagram)',
                            url: 'https://www.youtube.com/embed/uxzhCDQ7On0?autoplay=1',
                            time: '2:45',
                        },
                        {
                            id: 'what-is-an-operator-code',
                            name: 'What is an operator (code)',
                            url: 'https://www.youtube.com/embed/nTjd0A8Fzmc?autoplay=1',
                            time: '3:36',
                            next: 'passing-data-to-an-operator'
                        },
                        {
                            id: 'passing-data-to-an-operator',
                            name: 'Passing data to an operator',
                            url: 'https://www.youtube.com/embed/oN3Pm0ceS2k?autoplay=1',
                            time: '1:04',
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
                            url: 'https://www.youtube.com/embed/2K0_tSYEr3A?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/2K0_tSYEr3A?autoplay=1&start=33',
                            time: '2:12',
                            next: 'filter',
                        },
                        {
                            id: 'filter',
                            name: 'Filter',
                            url: 'https://www.youtube.com/embed/uQ01aXSi0mU?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/uQ01aXSi0mU?autoplay=1&start=42',
                            time: '2:24',
                            next: 'reduce',
                        },
                        {
                            id: 'reduce',
                            name: 'Reduce',
                            url: 'https://www.youtube.com/embed/OLnrBK8gnXo?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/OLnrBK8gnXo?autoplay=1&start=55',
                            time: '4:46',
                            next: 'scan',
                        },
                        {
                            id: 'scan',
                            name: 'Scan',
                            url: 'https://www.youtube.com/embed/7wSTsPTOUyw?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/7wSTsPTOUyw?autoplay=1&start=49',
                            time: '4:43',
                            next: 'take',
                        },
                        {
                            id: 'take',
                            name: 'Take',
                            url: 'https://www.youtube.com/embed/MllusI56wpQ?autoplay=1',
                            skipUrl : 'https://www.youtube.com/embed/MllusI56wpQ?autoplay=1&start=50',
                            time: '2:49',
                            next: 'tap',
                        },
                        {
                            id: 'tap',
                            name: 'Tap',
                            url: 'https://www.youtube.com/embed/wKppV0gi3Iw?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/wKppV0gi3Iw?autoplay=1&start=39',
                            time: '2:59',
                            next: 'takeUntil',
                        },
                        {
                            id: 'takeUntil',
                            name: 'TakeUntil',
                            url: 'https://www.youtube.com/embed/tyIyUlkLhwc?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/tyIyUlkLhwc?autoplay=1&start=58',
                            time: '3:58',
                            next: 'debounceTime',
                        },
                        {
                            id: 'debounceTime',
                            name: 'DebounceTime',
                            url: 'https://www.youtube.com/embed/sj0X-TaQU00?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/sj0X-TaQU00?autoplay=1&start=99',
                            time: '',
                            next: 'mergeMap',
                        },
                        {
                            id: 'mergeMap',
                            name: 'MergeMap',
                            url: 'https://www.youtube.com/embed/GcrBvwqN4Ro?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/GcrBvwqN4Ro?autoplay=1&start=157',
                            time: '7:29',
                            next: 'switchMap',
                        },
                        {
                            id: 'switchMap',
                            name: 'SwitchMap',
                            url: 'https://www.youtube.com/embed/vf4kwUA-XeE?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/vf4kwUA-XeE?autoplay=1&start=157',
                            time: '8:58',
                            next: 'concatMap',
                        },
                        {
                            id: 'concatMap',
                            name: 'ConcatMap',
                            url: 'https://www.youtube.com/embed/ggRflBfazMU?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/ggRflBfazMU?autoplay=1&start=113',
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
                            url: 'https://www.youtube.com/embed/jjv1DolUG9Y?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/jjv1DolUG9Y?autoplay=1&start=56',
                            time: '3:34',
                            next: 'timer',
                        },
                        {
                            id: 'timer',
                            name: 'Timer',
                            url: 'https://www.youtube.com/embed/2s2vU-UwOwQ?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/2s2vU-UwOwQ?start=44&autoplay=1',
                            time: '3:49',
                            next: 'of',
                        },
                        {
                            id: 'of',
                            name: 'Of',
                            url: 'https://www.youtube.com/embed/VuzGTdLW0Zo?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/VuzGTdLW0Zo?autoplay=1&start=42',
                            time: '2:06',
                            next: 'merge',
                        },
                        {
                            id: 'merge',
                            name: 'Merge',
                            url: 'https://www.youtube.com/embed/-oDU_p172tk?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/-oDU_p172tk?autoplay=1&start=55',
                            time: '4:16',
                            next: 'combineLatest'
                        },
                        {
                            id: 'combineLatest',
                            name: 'CombineLatest',
                            url: 'https://www.youtube.com/embed/BhxtI8nH40g?autoplay=1',
                            skipUrl: 'https://www.youtube.com/embed/BhxtI8nH40g?autoplay=1&start=87',
                            time: '8:04',
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
