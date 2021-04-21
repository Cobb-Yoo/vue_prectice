<template>
    <div>
        <h1> Welcome slave!</h1>
        <input type="text" v-model="input" @keyup.enter="addData"/>

        <table class="table table-bordered">
            <tr :key="d" v-for="(d,i) in options">
                <td>{{d}}</td>
                <td>{{i}}</td>
                <button @click="removeData(i,d)">삭제</button>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data(){
        return{
            options:[]
        };
    },
    created(){
        if(localStorage.length > 0){
            for(var i=0;i< localStorage.length;i++){
                this.options.push(localStorage.key(i));
            }
        }
    },
    methods:{
        addData(){
            if(this.input !== ''){
                this.options.push({t: this.input});
                localStorage.setItem(this.input, this.input);
                this.input = "";
            }
        },
        removeData(index, data){
            localStorage.removeItem(data);
            this.options.splice(index,1);
        }
    },
};
</script>

