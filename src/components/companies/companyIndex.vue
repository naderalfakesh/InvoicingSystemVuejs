<template>
    <div>
        <button @click="createCompany()" class="btn btn-dark" >Yeni firma kaydet</button>
        <table class="table">
            <thead>
                <th scope="col">#</th>
                <th scope="col">Firma</th>
                <th scope="col">Email</th>
                <th scope="col">Telefon</th>
                <th scope="col">Website</th>
                <th scope="col">Adres</th>
                <th scope="col">Aksyon</th>
            </thead>
            <tbody>
                <tr v-for="(company,index) in companies" v-bind:key="index">
                    <td>{{index+1}}</td>
                    <td>{{company.name}}</td>
                    <td>{{company.email}}</td>
                    <td>{{company.phone}}</td>
                    <td>{{company.website}}</td>
                    <td>{{company.address}}</td>
                    <td>
                        <button @click="showCompany(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                        <button @click="editCompany(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                        <button @click="deleteCompany(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    data: function(){
        return {
            companies:[
                {
                    id: 1,
                    name: "name 1",
                    type: "type 1",
                    email: "email 1",
                    website: "website 1",
                    phone: "phone 1",
                    taxAdmin:"tax admin 1",
                    taxNumber:"tax number 1",
                    address:"address 1",
                },
                {
                    id: 2,
                    name: "name 2",
                    type: "type 2",
                    email: "email 2",
                    website: "website 2",
                    phone: "phone 2",
                    taxAdmin:"tax admin 2",
                    taxNumber:"tax number 2",
                    address:"address 2",
                },
                {
                    id: 3,
                    name: "name 3",
                    type: "type 3",
                    email: "email 3",
                    website: "website 3",
                    phone: "phone 3",
                    taxAdmin:"tax admin 3",
                    taxNumber:"tax number 3",
                    address:"address 3",
                }
            ]
        };
    },
    methods:{
        createCompany: function(){

        },
        showCompany: function(index){
            this.$router.push({name: 'companyView' , params: {company: this.companies[index] } })
        },
        editCompany: function(index){

        },
        deleteCompany: function(index){

        },
    } 
}
</script>

<style>

</style>
