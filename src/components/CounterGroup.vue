<template>
    <div class="counterGroup">
        <input v-model="counterNum" @input="initCounters">
        <br>
        <Counter v-for="n in getNum()" v-bind:key="n" v-bind:index = "n" v-bind:counter=counters[n-1] v-on:update="updateCounter" />
        <span>sum is :{{sum}}</span>
    </div>
</template>

<script>
    import Counter from './Counter.vue'

    export default {
        name: 'CounterGroup',
        components: {
            Counter
        },


        data() {
            return {
                counterNum: 0,
                counters:[],
                sum:0
            }
        },
        methods:{
            getNum : function(){
                if (this.isNumber(this.counterNum)) {
                    return parseInt(this.counterNum)
                }
                else {
                  return 0;
                }
            },
            isNumber : function (n) {
       return !isNaN(parseFloat(n)) && isFinite(n);
            },
            updateCounter : function(data){
                this.counters[data.index-1] = data.value;
                this.getSum();

            },
            getSum : function () {
                this.sum = 0;
                for (let i = 0 ;i < this.counters.length; i++) {
                    this.sum += this.counters[i];
                }
            },
            initCounters : function () {
                let size = this.getNum();
                if(size === 0){
                    this.counters = [];
                }
                else {
                    this.counters = new Array(size);
                }
                for (let i = 0;i < this.counters.length;i++){
                    this.counters[i] = i+1;
                }
                this.getSum();
            }
        }
    }
</script>


