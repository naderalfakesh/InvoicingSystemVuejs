<template>
<div>
    <div class="card">
        <div class="card-body">
            <button @click="lsdCreate()" class="btn btn-sm btn-dark">Yeni rehosa talebi</button>
        </div>
    </div>
    <div class="card my-3">
        <div class="card-body">
            <table class="table table-sm">
                <thead>
                    <th scope="col">Sipariş tarihi</th>
                    <th scope="col">Müşteri</th>
                    <th scope="col">Model</th>
                    <th scope="col">Motor markası</th>
                    <th scope="col">İstenen tarihi</th>
                    <th scope="col">Statüs</th>
                    <th scope="col">Aksiyon</th>
                </thead>
                <tbody>
                    <tr v-for="(lsd,index) in lsds" v-bind:key="index">
                        <td>{{lsd.orderDate}}</td>
                        <td>{{lsd.company}}</td>
                        <td>{{lsd.model}}</td>
                        <td>{{lsd.motorInfo.brand}}</td>
                        <td>{{lsd.wantedDeliveryDate}}</td>
                        <td>{{lsd.status}}</td>
                        <td>
                            <button @click="lsdShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                            <button @click="lsdEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                            <button @click="lsdDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>
    
</template>

<script>
export default {
    name: "lsdCreate",
    data: function(){
        return {
            lsds:[
                {
                id: 1,
                company: "Ersel",
                orderDate: "02-01-1991", 
                salesPrice: "500 Euro", 
                commercialConditions: "3 days bedava", 
                wantedDeliveryDate: "02-02-1991", 
                model: "LSDEmini",
                serialNumber: "19001",
                productionDate: "02-01-1991",
                status: "Teslim edilmiştir",
                motorInfo: {
                    brand: "ABB",
                    statorVoltage: "6600V",
                    statorCurrent: "38A",
                    rotorVoltage: "1250V",
                    rotorCurrent: "410A",
                    burshLifitng: "Mevcut"
                },
                lsdInfo: {
                    motor: "0.55kw",
                    vfd:    "CFW10",
                    gearbox: "DSV",
                    contactor: "HOMA"
                },
                testInfo:{
                    tester: "Nader Alfakesh",
                    testDate: "02-01-1991",
                    proplem: "Test sağlıklı"
                },
                deliveryDate: "02-01-1991",
                CommessioningInfo: {
                    commisioner: "Kadir Özböler" ,
                    enduser: "Maden yapı",
                    commesionDate: "02-01-1991",
                    address: "Fas kasablanka",
                    conductivity: "10ms/cm 40C",
                    notes: "pompa bozuktu , değiştirildi"
                }
            }
        ],

        };
    },
    methods:{
        lsdShow: function(index){
            this.$router.push({name:'lsdView',params: {lsd: this.lsds[index]}})
        },
        lsdEdit: function(index){
            this.$router.push({name:'lsdEdit',params: {lsd: this.lsds[index]}})
        },
        lsdDelete: function(index){
            alert("Are you sure you want to delete this number" + index)
        },
        lsdCreate: function(){
            this.$router.push({name:'lsdCreate',params: {lsd: null} })
        },
       
    },

}
</script>

<style>

</style>
