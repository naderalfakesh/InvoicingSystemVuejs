<template>
  <div>
    <button @click="create()" class="btn btn-dark btn-sm" >Yeni oluştur</button>
    <table class="table table-sm">
        <thead>
            <th v-for="(row,index) in header" v-bind:key="index" scope="col">{{row}}</th>
            <th scope="col">Aksyon</th>
        </thead>
        <tbody>
            <tr v-for="(row,i) in data" v-bind:key="i">
                <td v-for="(cell,j) in row" v-bind:key="j">{{typeof(cell) == 'string' ? cell.slice(0,20) : cell  }}</td>
                <td>
                    <button @click="show(row.id)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                    <button @click="edit(row.id)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                    <button @click="del(row.id)" class="btn btn-sm btn-danger" title="Sil">S</button>
                </td>
            </tr>
        </tbody>
    </table>
  </div>
</template>

<script>

export default {
name: 'indexer',
props: ['data','header'],
data: function(){
        return {};
},
methods: {
    create: function(){
    //     this.$router.push({name: 'companyCreate' , params: {company: null } })
    },
    show: function(index){
        // alert(index);
        this.$router.push({name: 'productView' , params: {'product': this.data[index] } })
    },
    edit: function(index){
        alert(index);
    //     this.$router.push({name: 'companyEdit' , params: {company: this.companies[index] } })
    },
    del: function(index){
        alert(index);
        //     alert("Are you sure you want to delete this" + index)
    },
},

}
</script>

<style>

</style>