<template>
    <b-col cols="12"  md="4">



        <b-tabs v-model='tabIndex' content-class="mt-3" fill>
            <info/>

            <experience/>

            <project/>

            <education/>

            <more/>

        </b-tabs>
        <div class="text-center ">
            <b-button-group class="mt-4">
                <b-button variant="dark" @click="tabIndex--">{{$t('buttons.previous')}}</b-button>
                <b-button variant="dark" @click="tabIndex++">{{$t('buttons.next')}}</b-button>
            </b-button-group>
        </div>
    </b-col>
</template>

<script>
    import info         from "./tabs/info.vue";
    import experience   from "./tabs/experience.vue";
    import project      from "./tabs/project.vue";
    import education    from "./tabs/education.vue";
    import more         from "./tabs/more.vue";

    export default {
        name: 'appSidebar',
        components: {
            experience,
            project,
            education,
            info,
            more,
        },
        computed:{
            tabIndex: {
                get() {
                    return this.$store.state.tabs.index
                },
                set(value) {
                    this.$store.state.tabs.index = value
                }
            }
        }
    }
</script>