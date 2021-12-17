<template>
    <main>
        <GenreSelection @selectedGenre="changeSelect"/>
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
import GenreSelection from '@/components/GenreSelection.vue'
import axios from "axios";
export default {
    name: 'Records',
    components: {
        CardRecord,
        GenreSelection,
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
             if (this.selectedGenre === 'all') {
                return this.recordList
            }
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
        changeSelect(selezione){
            this.selectedGenre = selezione
            console.log(this.selectedGenre);
        }
        
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