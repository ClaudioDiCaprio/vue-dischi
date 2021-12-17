<template>
    <main>
        <section>
            <CardRecord
                v-for="record, i in RecordList"
                :key="i"
                :elements="record"
            />
        </section>
    </main>
</template>



<script>
import CardRecord from '@/components/CardRecord.vue'
import axios from "axios";
export default {
    name: 'Records',
    components: {
        CardRecord,
    },
    data() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            recordList: [],
            selectedGenre : ''
        }
    },
    created() {
        this.getRecord();
    },
    computed : {
        RecordList(){
            return this.recordList.filter((item) => {
                return item.genre.includes(this.selectedGenre)
            })
        }
    },
    methods: {
        getRecord() {
            axios
            .get(this.apiUrl)
            .then((result) => {
                this.recordList = result.data.response
            })
        },
        
    }
}
</script>

<style scoped lang="scss">
main {
    section {
        width: 80%;
        margin: 50px auto 0;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
}
</style>