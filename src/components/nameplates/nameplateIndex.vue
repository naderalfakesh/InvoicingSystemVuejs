<template>
    <div>
        <div class="card border-primary my-3">
            <div class="card-header text-primary">
                <h5>Teklifler</h5>
            </div>
            <div class="card-body">
                <table class="table table-sm">
                    <thead class="table-primary">
                        <th scope="col">Ürün kodu</th>
                        <th scope="col">model</th>
                        <th scope="col">Güç</th>
                        <th scope="col">Gövde</th>
                        <th scope="col">kutup sayısı</th>
                        <th scope="col">Seri numarası</th>
                        <th scope="col">Aksion</th>
                    </thead>
                    <tbody> 
                        <tr v-for="(nameplate,index) in nameplates" :key="index" >
                            <td>{{nameplate.materialNumber}}</td>
                            <td>{{nameplate.model}}</td>
                            <td>{{nameplate.power}}</td>
                            <td>{{nameplate.frame}}</td>
                            <td>{{nameplate.pole}}</td>
                            <td>{{nameplate.serialNumber}}</td>
                            <td>
                                <button @click="nameplateShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                                <button @click="nameplateEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                                <button @click="nameplateDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
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
    name: "offerIndex",
    data: function(){
        return {
            nameplates:[
                {
                    model:"W22",
                    productionDate: "20MAY2019",
                    serialNumber: "1049107714",
                    materialNumber: "14888427",
                    frame: "250S/M",
                    pole: "04",
                    protectionClass: "IP55",
                    insulationClass: "H",
                    deltaT: "80",
                    duty: "S1",
                    serviceFactor: "1.00",
                    smokeClass: "S2 400 C-2h",
                    voltage:["380 / 660","400 / 690","415 / -","460 / -"],
                    frequency:["50","60"],
                    power: "55",
                    speed:["1470","1475","1475",""],
                    current:["104 / 60","100 / 57,7","97,4 / -","87,0 / -"],
                    powerFactor:["0,86","0,85","0,84","0,85"],
                    IECode:"IE2",
                    eff100:["93,5","93,1","93,1"],
                    eff75:["93,5","93,2","92,9"],
                    eff50:["93,7","93,2","92,1"],
                    deBearing: "6314-C3",
                    ndeBearing: "6314-C3",
                    deGreaseQTY: "53",
                    ndeGreaseQTY: "53",
                    grease: "KRYTOX GPL 225",
                    greasePeriod: "20000",
                    nema1: "NEMA Eff 93,7% 75HP 460V 60 Hz 1775RP",
                    nema2: "87,9 A PF 0,85 Des A Code H SF 1,15",
                    altitude: "1000",
                    weight: "384",
                    teao1: "TEAO - Totally Enclosed Air Over",
                    teao2: "S1 40C only with FAN coupled",
                },
            ]
        };
    },
    methods:{
        nameplateShow: function(index){
            this.$router.push({name:'nameplateView',params: {nameplate: this.nameplates[index]}})
        },
        nameplateEdit: function(index){
            this.$router.push({name:'nameplateEdit',params: {nameplate: this.nameplates[index]}})
        },
        nameplateDelete: function(index){
            alert(index)
        },
        nameplateCreate: function(){
            this.$router.push({name:'nameplateCreate',params: {nameplate: null} })
        },
    },
}
</script>

<style>

</style>
