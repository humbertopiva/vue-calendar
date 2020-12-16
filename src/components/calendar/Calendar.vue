<template>
    <div class="calendar-container">
        <div class="calendar-date" v-for="aula of datas">
            <span class="date badge"> {{ aula.date }} </span>
            <template v-for="schedule of aula.schedules">
                <span class="class badge badge-primary" v-for="work_schedule of schedule.work_schedules">{{work_schedule.agenda.start_hour}}:{{work_schedule.agenda.start_minute}}</span>
            </template>
        </div>
    </div>
</template>
<script>
    export default{
        props: ['datas']
    }
</script>

<style scoped>

.calendar-container {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    width: 60%;
    margin: 10px;
}

.calendar-date {
    display: flex;
    flex-direction: column;
}

.date {
    margin: 5px 5px;
}

.class {
    margin: 5px 5px;
}

</style>