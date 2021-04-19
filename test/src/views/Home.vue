<template>
    <div>
        <h1> Welcome slave!</h1>
        <input type="text" v-model="input" @keyup.enter="addData"/>

        <table class="table table-bordered" v-if="tableShow">
            <tr :key="i" :value="d.v" v-for="(d,i) in options">
                <td>{{d.t}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data(){
        return{
            input: "",
            options:[],
            tableShow: true
        };
    },
    methods:{
        addData(){
            this.options.push({t: this.input});
            localStorage.setItem(this.newTodoItem, this.input);
            this.input = "";
        }
    },
};
</script>

