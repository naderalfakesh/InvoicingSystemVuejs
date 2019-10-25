<template>
<div class="container"> 
    <div class="card border-primary">
        <div class="card-header bg-primary text-white">
            <h5>Sipariş detayları</h5>
        </div>
        <div class="card-body">
            <div class="row">
                <div class="col">
                    <b>Müşteri</b>
                    <select v-model="lsdCreate.company" class="form-control">
                        <option v-for="(company,index) in companies" :key="index" :value="company">{{company.name}}</option>
                    </select>
                </div>
                <div class="col">
                    <b>Sipariş tarihii</b>
                    <input v-model="lsdCreate.orderDate" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>İstenilen tarihi</b>
                    <input v-model="lsdCreate.wantedDeliveryDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <b>Rheosta modeli</b>
                    <input v-model="lsdCreate.model" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>Satış bedeli</b>
                    <input v-model="lsdCreate.salesPrice" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>Teslim tarihi</b>
                    <input v-model="lsdCreate.deliveryDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col-9 ">
                    <b>Ticari koşullar</b>
                    <textarea v-model="lsdCreate.commercialConditions" class="form-control"  rows="3"></textarea>
                </div>
            </div>
        </div>
    </div>

    <div class="card border-info mt-3">
        <div class="card-header bg-info text-white">
            <h5>Ana Motor detayları</h5>
        </div>
        <div class="card-body">
            <div class="row">
                <div class="col">
                    <h5>Marka</h5>
                    <input v-model="lsdCreate.motorInfo.brand" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Güç</h5>
                    <input v-model="lsdCreate.motorInfo.power" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Kutup sayısı</h5>
                    <input v-model="lsdCreate.motorInfo.poles" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Stator gerilimi</h5>
                    <input v-model="lsdCreate.motorInfo.statorVoltage" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Rotor gerilmi</h5>
                    <input v-model="lsdCreate.motorInfo.rotorVoltage" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Stator akımı</h5>
                    <input v-model="lsdCreate.motorInfo.statorCurrent" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Rotor akımı</h5>
                    <input v-model="lsdCreate.motorInfo.rotorCurrent" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
            </div>
        </div>
    </div>
    <div class="card border-success my-3">
        <div class="card-header bg-success text-white">
            <h5>Rheosta detayları</h5>
        </div>
        <div class="card-body">
            <div class="row">
                <div class="col">
                    <h5>Elektrod motoru</h5>
                    <input v-model="lsdCreate.lsdInfo.motor" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Sürücü</h5>
                    <input v-model="lsdCreate.lsdInfo.vfd" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Redüktör</h5>
                    <input v-model="lsdCreate.lsdInfo.gearbox" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                    
                <div class="col">
                    <h5>Kontaktör</h5>
                    <input v-model="lsdCreate.lsdInfo.contactor" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Seri numarası</h5>
                    <input v-model="lsdCreate.lsdInfo.serialNumber" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>İmalat tarihi</h5>
                    <input v-model="lsdCreate.lsdInfo.productionDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
            </div>
        </div>
    </div>
    <div class="card border-warning my-3">
        <div class="card-header bg-warning">
            <h5>Test</h5>
        </div>
        <div class="card-body">
            <div class="row">
                <div class="col">
                    <h5>Test yapan</h5>
                    <input v-model="lsdCreate.testInfo.tester" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Test Tarihi</h5>
                    <input v-model="lsdCreate.testInfo.testDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Test sonucu</h5>
                    <input v-model="lsdCreate.testInfo.testResult" type="text" class="form-control">
                </div>
            </div>
        </div>
    </div>
    <div class="card border-secondary my-3">
        <div class="card-header bg-secondary text-white">
            <h5>Devreya alma</h5>
        </div>
        <div class="card-body">
        <div class="row">
            <div class="col">
                <h5>Devreya alan</h5>
                <input v-model="lsdCreate.commissioningInfo.commissioner" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Son kullanıcı</h5>
                <input v-model="lsdCreate.commissioningInfo.enduser" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Adres</h5>
                <input v-model="lsdCreate.commissioningInfo.address" type="text" class="form-control">
            </div>
            <div class="w-100"></div>
            <div class="col">
                <h5>Tarih</h5>
                <input v-model="lsdCreate.commissioningInfo.commissionDate" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>İletkenlik</h5>
                <input v-model="lsdCreate.commissioningInfo.conductivity" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Not</h5>
                <input v-model="lsdCreate.commissioningInfo.notes" type="text" class="form-control">
            </div>
            </div>
        </div>
    </div>
    <div class="row m-3">
        <div class="col  text-center">
            <button class="btn btn-primary" @click="save()">Kaydet</button>
        </div>
    </div>

</div>
    
</template>

<script>
/* eslint-disable */
import axios from 'axios'
export default {
    name: "lsdCreate",
    props: ["lsd"],
    data: function(){
        return {
            lsdCreate:
            {
                company: "",
                orderDate: "", 
                salesPrice: "", 
                commercialConditions: "", 
                wantedDeliveryDate: "", 
                model: "",
                deliveryDate: "",
                status: "",
                motorInfo: {
                    brand: "",
                    power: "",
                    poles:  "",
                    statorVoltage: "",
                    statorCurrent: "",
                    rotorVoltage: "",
                    rotorCurrent: "",
                    burshLifitng: false
                },
                lsdInfo: {
                    motor: "",
                    vfd:    "",
                    gearbox: "",
                    contactor: "",
                    serialNumber: "",
                    productionDate: "",
                },
                testInfo:{
                    tester: "",
                    testDate: "",
                    testResult: ""
                },
                commissioningInfo: {
                    commissioner: "" ,
                    enduser: "",
                    address: "",
                    commissionDate: "",
                    conductivity: "",
                    notes: ""
                }
            },
            companies: []
        };
    },
    methods:{
        save: function (){
            if(this.lsd != null){
                this.update()
            }
            else{
                this.create()
            }
        },  
        update: function (){
            this.lsdCreate.status = "Update"
            axios
            .put('http://localhost:5000/lsd',{
            lsd : this.lsdCreate
            })
            .then(res => {
                console.log( res.data);
                this.$router.push({name: 'lsdIndex'})
                })
            .catch(err => console.log('Update() ' + err))
        },
        create: function(){
            this.lsdCreate.status = "New"
            axios
            .post('http://localhost:5000/lsd',{
            lsd: this.lsdCreate
            })
            .then(res => {
                console.log( res.data)
                this.$router.push({name: 'lsdIndex'})
                })
            .catch(err => console.log('Create() ' + err))
        },
    },
    created: function(){
        if (this.lsd != null) {
            this.lsdCreate = this.lsd;
        }
        axios
        .get('http://localhost:5000/company')
        .then(res => {
        this.companies = res.data
        })
        .catch(err => console.log(err))
    },
}
</script>

<style>

</style>
