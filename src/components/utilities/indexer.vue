<template>
  <div>
    <button @click="create()" class="btn btn-dark btn-sm" >Yeni oluştur</button>
    <table class="table table-sm">
        <thead>
            <th scope="col">#</th>
            <th v-for="(row,index) in header" v-bind:key="index" scope="col">{{row}}</th>
            <th scope="col">Aksyon</th>
        </thead>
        <tbody>
            <tr v-for="(row,i) in data" v-bind:key="i">
                <td>{{i+1}}</td>
                <td v-for="(value,key,j) in header" v-bind:key="j">{{typeof(row[key]) == 'string' ? row[key].slice(0,20) : row[key]  }}</td>
                <td>
                    <button @click="show(i)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                    <button @click="edit(i)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                    <button @click="del(i)" class="btn btn-sm btn-danger" title="Sil">S</button>
                </td>
            </tr>
        </tbody>
    </table>
  </div>
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
name: 'indexer',
props: ['data','header','nesne'],
data: function(){
        return {};
},
methods: {
    create: function(){
        this.$router.push({name: this.nesne+'Create' , params: { [this.nesne] : null } })
    },
    show: function(index){
        this.$router.push({name: this.nesne+'View' , params: { [this.nesne] : this.data[index] } })
    },
    edit: function(index){
        this.$router.push({name: this.nesne+'Edit' , params: { [this.nesne] : this.data[index] } })
    },
    del: function(index){
        axios
        .delete('http://localhost:5000/'+this.nesne+'/'+this.data[index]._id)
        .then(res => {
           console.log(res.data);
           this.data.splice(index,1)
            })
        .catch(err => console.log(err))
    },
},

}
</script>

<style>

</style>