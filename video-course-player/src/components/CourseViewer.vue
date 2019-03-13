<template>
    <div class="course-viewer">
        <v-list two-line subheader>
            <template v-for="category in input.categories">
                <v-subheader
                        inset>{{category.name}}
                </v-subheader>

                <v-list-tile
                        v-for="lecture in category.lectures"
                        :key="lecture.name"
                        avatar
                        v-on:click="selectLecture(lecture)"
                        :class="{highlighted: lecture.id === activeId}"
                >

                    <v-list-tile-content>
                        <v-list-tile-title>{{ lecture.name }}</v-list-tile-title>
                        <v-list-tile-sub-title><v-icon size="14">access_time</v-icon>
                            <span style="margin-left: 5px">{{ lecture.time }}</span></v-list-tile-sub-title>
                    </v-list-tile-content>

                    <v-list-tile-action>
                        <v-btn icon ripple>
                            <v-icon>play_circle_filled</v-icon>
                        </v-btn>
                    </v-list-tile-action>
                </v-list-tile>

                <v-divider inset></v-divider>
            </template>
        </v-list>
        <div class="video">
            <youtube-player :url="url"></youtube-player>
        </div>
    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';
    import YoutubePlayer from '@/components/YoutubePlayer.vue';

    @Component({
        components: {
            YoutubePlayer,
        }
    })
    export default class CourseViewer extends Vue {
        @Prop() public input!: any;

        public categories: any[];
        public url: string;
        public activeId: string;
        public lectures: any[];
        public searchParams = new URLSearchParams(window.location.search);

        data() {
            return {
                url: undefined,
            }
        };

        public created() {
            this.categories = this.input.categories;
            console.log(this.categories);
            this.lectures = this.categories
                .map((category) => category.lectures)
                .reduce((acc, cur) => ([...acc, ...cur]), []);
            const lectureId = this.searchParams.get('lectureId');
            this.activeId = this.searchParams.get('lectureId') || this.input.categories[0].lectures[0].id;
            if(!lectureId) {
                this.searchParams.set('lectureId', this.activeId);
                window.history.replaceState({}, '', `${location.pathname}?${this.searchParams}`);
            }
            const lectureFound = this.lectures.find((lec) => lec.id === this.activeId);
            this.url = lectureFound.url;
        }

        public selectLecture(lecture: any) {
            console.log('setting lecture', lecture, this.url);
            this.url = lecture.url;
            console.log(this.url);
            this.activeId = lecture.id;
            this.searchParams.set('lectureId', lecture.id);
            window.history.replaceState({}, '', `${location.pathname}?${this.searchParams}`);
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    @media only screen and (max-width: 769px) {
        .course-viewer {
            display:flex;
            flex-direction: column-reverse;
            height: 100vh;
            align-items: stretch;
        }

        .video {
            min-height: calc(100vw / 1.6);
        }
    }
    @media only screen and (min-width: 769px) {
        .course-viewer {
            display:flex;
            flex-direction: row;
            height: 100vh;
            align-items: stretch;
        }

        .v-list {
            width: calc(100vw - 100vh * 1.6);
            min-width: 306px;
        }
    }

    .v-list {
        overflow-y: scroll;
    }

    .video {
        flex: 1;
        display: flex;
    }

    iframe {
        flex: 1;
    }

    .highlighted {
        background: rgba(255,255,255,0.08);
    }
</style>
