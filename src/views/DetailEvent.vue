<template>
    <div>
        <div class="row">
            <div class="col-8">
                <h4>{{ Event.name }}</h4>
            </div>
            <div class="col-4 d-grid">
                <button class="btn btn-primary">Register for this event</button>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col-12">
                <TableEvent :EventData="Event"></TableEvent>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import TableEvent from '../components/table-event.vue'


export default {
    components: { TableEvent },
        name: 'DetailEvent',
        
    data(){
        return{
            OrganizerSlug: this.$route.params.SlugOrganizer,
            EventSlug: this.$route.params.SlugEvent,
            Event:{}
        }
    },
    mounted(){
        this.DatosEvento();
    },
    methods:{
        DatosEvento(){
            axios.get('organizer/' + this.OrganizerSlug + '/events/' + this.EventSlug)
            .then((response) => {
                if(response.status == 200){
                    this.Event = response.data;
                }
            })
        }
    }
}
</script>