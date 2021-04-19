<template>
    <div>
        <h1> Welcome to {{title}}!</h1>
        <input type="text" v-model="input1" />
        <button type="button" @click="getData">Get</button>
        <button type="button" @click="setData">Set</button>

        <select class="form-control" v-model="region" @change="changeRegion">
            <option :key="i" :value="d.v" v-for="(d,i) in options">{{d.t}}</option>
        </select>

        <table class="table table-bordered" v-if="tableShow">
            <tr :key="i" :value="d.v" v-for="(d,i) in options">
                <td>{{d.v}}</td>
                <td>{{d.t}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data(){
        return{
            title: "개발자의 품격",
            title2: "Seoul",
            input1: "abc",
            options:[
                {v:"S", t: "Seoul"},
                {v:"J", t: "Jeju"},
                {v:"B", t: "Busan"},
            ],
            region: "J",
            tableShow: false
        };
    },
    methods:{
        getData(){
            alert(this.input1);
        },
        setData(){
            this.input1 = "12345";
        },
        changeRegion(){
            alert(this.region);
        }
    }
};
</script>

