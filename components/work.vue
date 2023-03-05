<template lang="html">
    <div>
        <h2>Homework</h2>
        <h4 v-for="item in work" :key="item.work_name" > <p><b class="red--text">WorkName:</b> {{ item.work_name}}</p> <p><b class="red--text">WorkDetails:</b>{{ item.work_details }}</p>  
            <p><b class="red--text">SubjectName:</b>{{ item.sub_name }}</p>  <p><b class="red--text">Deadline:</b>{{ item.dead_line  }}</p> </h4>
    </div>
</template>
<script>
export default {
    data() {
        return {
            work:[
                {   
                    work_name: 'สอบเก็บคะแนน',
                    work_details: 'เก็บคะแนนสามสิบเปอร์',
                    sub_name: 'คณิตศาสตร์',
                    dead_line: '2021/04/03'
                },
                {   
                    work_name: 'แบบฝึกหัด 1',
                    work_details: 'ข้อ1 2 3',
                    sub_name: 'ภาษาไทยเสริมสร้าง',
                    dead_line: '2021/04/03'
                },
        ]
        }
    }
}
</script>
<style lang="css">
    
</style>