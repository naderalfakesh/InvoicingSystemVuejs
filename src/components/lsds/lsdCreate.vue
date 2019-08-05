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
                    <input v-model="lsd.company" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>Sipariş tarihii</b>
                    <input v-model="lsd.orderDate" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>İstenilen tarihi</b>
                    <input v-model="lsd.wantedDeliveryDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <b>Rheosta modeli</b>
                    <input v-model="lsd.model" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>Satış bedeli</b>
                    <input v-model="lsd.salesPrice" type="text" class="form-control">
                </div>
                <div class="col">
                    <b>Teslim tarihi</b>
                    <input v-model="lsd.deliveryDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col-9 ">
                    <b>Ticari koşullar</b>
                    <textarea v-model="lsd.commercialConditions" class="form-control"  rows="3"></textarea>
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
                    <input v-model="lsd.motorInfo.brand" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Güç</h5>
                    <input v-model="lsd.motorInfo.power" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Kutup sayısı</h5>
                    <input v-model="lsd.motorInfo.poles" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Stator gerilimi</h5>
                    <input v-model="lsd.motorInfo.statorVoltage" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Rotor gerilmi</h5>
                    <input v-model="lsd.motorInfo.rotorVoltage" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Stator akımı</h5>
                    <input v-model="lsd.motorInfo.statorCurrent" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Rotor akımı</h5>
                    <input v-model="lsd.motorInfo.rotorCurrent" type="text" class="form-control">
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
                    <input v-model="lsd.lsdInfo.motor" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Sürücü</h5>
                    <input v-model="lsd.lsdInfo.vfd" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Redüktör</h5>
                    <input v-model="lsd.lsdInfo.gearbox" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                    
                <div class="col">
                    <h5>Kontaktör</h5>
                    <input v-model="lsd.lsdInfo.contactor" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Seri numarası</h5>
                    <input v-model="lsd.lsdInfo.serialNumber" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>İmalat tarihi</h5>
                    <input v-model="lsd.lsdInfo.productionDate" type="text" class="form-control">
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
                    <input v-model="lsd.testInfo.tester" type="text" class="form-control">
                </div>
                <div class="col">
                    <h5>Test Tarihi</h5>
                    <input v-model="lsd.testInfo.testDate" type="text" class="form-control">
                </div>
                <div class="w-100"></div>
                <div class="col">
                    <h5>Test sonucu</h5>
                    <input v-model="lsd.testInfo.testResult" type="text" class="form-control">
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
                <input v-model="lsd.commissioningInfo.commissioner" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Son kullanıcı</h5>
                <input v-model="lsd.commissioningInfo.enduser" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Adres</h5>
                <input v-model="lsd.commissioningInfo.address" type="text" class="form-control">
            </div>
            <div class="w-100"></div>
            <div class="col">
                <h5>Tarih</h5>
                <input v-model="lsd.commissioningInfo.commissionDate" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>İletkenlik</h5>
                <input v-model="lsd.commissioningInfo.conductivity" type="text" class="form-control">
            </div>
            <div class="col">
                <h5>Not</h5>
                <input v-model="lsd.commissioningInfo.notes" type="text" class="form-control">
            </div>
            </div>
        </div>
    </div>
    <div class="row m-3">
        <div class="col  text-center">
            <button class="btn btn-primary ">Kaydet</button>
        </div>
    </div>

</div>
    
</template>

<script>


export default {
    name: "lsdCreate",
    data: function(){
        return {
            lsd:
            {
                id: 1,
                company: "Ersel",
                orderDate: "02-01-1991", 
                salesPrice: "500 Euro", 
                commercialConditions: "3 days bedava", 
                wantedDeliveryDate: "02-02-1991", 
                model: "LSDEmini",
                status: "delivered",
                motorInfo: {
                    brand: "ABB",
                    power: "2800",
                    poles:  "6",
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
                    contactor: "HOMA",
                    serialNumber: "19001",
                    productionDate: "02-01-1991",
                },
                testInfo:{
                    tester: "Nader Alfakesh",
                    testDate: "02-01-1991",
                    testResult: "Test sağlıklı geçmiştir"
                },
                deliveryDate: "02-01-1991",
                commissioningInfo: {
                    commissioner: "Kadir Özböler" ,
                    enduser: "Maden yapı",
                    address: "Fas kasablanka",
                    commissionDate: "02-01-1991",
                    conductivity: "10ms/cm 40C",
                    notes: "pompa bozuktu , değiştirildi"
                }
            }
        };
    },
}
</script>

<style>

</style>
