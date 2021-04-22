<template>
    <div>
        <h1> Welcome slave!</h1>
        <button @click="removeTotalData()">전체삭제</button>

        <input type="text" v-model="input" @keyup.enter="addData"/>

        <ul class="table table-bordered">
            <li :key="d" v-for="(d,i) in options">
                <td><button @click="removeData(i,d)">삭제</button> {{d}}</td>
            </li>
        </ul>
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
                if(localStorage.key(i) !== "loglevel:webpack-dev-server"){
                    this.options.push(localStorage.key(i));
                }
            }
        }
    },
    methods:{
        addData(){
            if(this.input !== ''){
                localStorage.setItem(this.input, this.input);
                this.options.push(this.input);
                this.input = "";
            }
        },
        removeData(index, data){
            localStorage.removeItem(data);
            this.options.splice(index,1);
        },
        removeTotalData(){
            var len = localStorage.length;
            localStorage.clear();
            for(var i=0;i<len;i++){
                this.options.splice(0,1);
            }
        }
    },
    watch:{

    }
};
</script>

