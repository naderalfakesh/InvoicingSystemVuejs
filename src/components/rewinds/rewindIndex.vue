<template>
    <div>
        <button @click="rewindCreate()" class="btn btn-sm btn-dark">Yeni sarım oluştur</button>
        <div class="card">
            <div class="card-body">
                <table class="table table-sm">
                    <thead>
                        <th scope="col">#</th>
                        <th scope="col">Müşteri</th>
                        <th scope="col">Güç</th>
                        <th scope="col">Kutup</th>
                        <th scope="col">Gerilim</th>
                        <th scope="col">Frekans</th>
                        <th scope="col">seri numarası</th>
                        <th scope="col">ürün kodu</th>
                        <th scope="col">Aksiyon</th>
                    </thead>
                    <tbody>
                        <tr v-for="(rewind,index) in rewinds" v-bind:key="index">
                            <td>{{index+1}}</td>
                            <td>{{rewind.customer}}</td>
                            <td>{{rewind.motor.power}}kW</td>
                            <td>{{rewind.motor.pole}}</td>
                            <td>{{rewind.actualVoltage}} => {{rewind.newVoltage}} [V]</td>
                            <td>{{rewind.actualFrequency}} => {{rewind.newFrequency}} [Hz]</td>
                            <td>{{rewind.serialNumber}}</td>
                            <td>{{rewind.materialNumber}}</td>
                            <td>
                                <button @click="rewindShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                                <button @click="rewindEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                                <button @click="rewindDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
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
    name: "rewindIndex",
    data: function(){
        return{
            rewinds: 
            [
                {
                    customer: "Dalgakıran",
                    serialNumber: "0987654321",
                    materialNumber: "1234567890",
                    productionDate: "01-01-2017",
                    motor: {
                        brand: "WEG", 
                        series: "W22", 
                        type: "Standard", 
                        power: 55,
                        speed: 1000,
                        voltage: 400,
                        frequency: 400,
                        effeciency: "IE2",
                        frame: 225,
                        pole:   6,
                    },
                    actualWire:[
                        {
                        quantity: 2,
                        guage: 0.5,
                        section:  0,  
                        },
                        {
                        quantity: 2,
                        guage: 0.5,
                        section:  0,  
                        },
                    ],
                    actualVoltage: 400,
                    actualCurrent: 1,
                    actualFrequency: 50,
                    actualNumberOfTurns: 15,
                    actualWireSection: 15,
                    newVoltage: 400,
                    newCurrent: 1,
                    newFrequency: 84,
                    newNumberOfTurns: 15,
                    newWireSection: 15,
                    newWire:[
                        {
                        quantity: 2,
                        guage: 0.5,
                        section:  0,  
                        },
                        {
                        quantity: 2,
                        guage: 0.5,
                        section:  0,  
                        },
                    ]
                }
            ]
        }
    },
    methods:{
        rewindCreate: function(){
            this.$router.push({name:'rewindCreate' })
        },
        rewindShow: function(index){
            this.$router.push({name: "rewindView" , params: {rewind: this.rewinds[index]} })
        },
        rewindEdit: function(index){
            this.$router.push({name: "rewindEdit" , params: {rewind: this.rewinds[index]} })
        },
        rewindDelete: function(index){
            alert("Are you sure you want to delete this" + index) 
        },
    }
}
</script>

<style>

</style>

