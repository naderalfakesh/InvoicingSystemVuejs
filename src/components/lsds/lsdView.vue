<template>
    <div>
        <div class="card border-success my-3">
            <div class="card-header text-success">
                <h5>Sipariş bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row">
                    <class class="col"><p>Müşteri: <strong>{{company}}</strong></p></class>
                    <class class="col"><p>model: <strong>{{model}}</strong></p></class>
                    <class class="col"><p>Sipariş tarihi: <strong>{{orderDate}}</strong></p></class>
                    <class class="col"><p>Statüs: <strong>{{status}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>İstenilen teslim tarihi: <strong>{{wantedDeliveryDate}}</strong></p></class>
                    <class class="col"><p>Gerçek teslim tarihi: <strong>{{deliveryDate}}</strong></p></class>
                    <class class="col"><p>Satış fiyatı: <strong>{{salesPrice}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Ticari koşulları: <strong>{{commercialConditions}}</strong></p></class>
                </div>
            </div>
        </div>

        <div class="card border-primary my-3">
            <div class="card-header text-primary">
                <h5>Ana motor bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row ">
                    <class class="col"><p>Marka: <strong>{{motorInfo.brand}}</strong></p></class>
                    <class class="col"><p>Güç: <strong>{{motorInfo.power}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Kutup sayısı: <strong>{{motorInfo.poles}}</strong></p></class>
                    <class class="col"><p>Fırça kaldırma opsyonu: <strong>{{motorInfo.burshLifitng}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Gerilim stator: <strong>{{motorInfo.statorVoltage}}</strong></p></class>
                    <class class="col"><p>Akım stator: <strong>{{motorInfo.statorCurrent}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Gerilim rotor: <strong>{{motorInfo.rotorVoltage}}</strong></p></class>
                    <class class="col"><p>Akım rotor <strong>{{motorInfo.rotorCurrent}}</strong></p></class>
                </div>
            </div>
        </div>

        <div class="card border-info my-3">
            <div class="card-header text-info">
                <h5>Sulu yol verici bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row ">
                    <class class="col"><p>Model: <strong>{{model}}</strong></p></class>
                    <class class="col"><p>Seri numarası: <strong>{{lsdInfo.serialNumber}}</strong></p></class>
                    <class class="col"><p>Ürün kodu: <strong>{{lsdInfo.productionDate}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Elektrod motoru: <strong>{{lsdInfo.motor}}</strong></p></class>
                    <class class="col"><p>Sürücü: <strong>{{lsdInfo.vfd}}</strong></p></class>
                    <class class="col"><p>Redüktör: <strong>{{lsdInfo.gearbox}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Kontaktor: <strong>{{lsdInfo.contactor}}</strong></p></class>
                </div>
            </div>
        </div>

        <div class="card border-warning my-3">
            <div class="card-header text-warning">
                <h5>Test bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row">
                    <class class="col"><p>Test yetkilisi: <strong>{{testInfo.tester}}</strong></p></class>
                    <class class="col"><p>Test tarihi: <strong>{{testInfo.testDate}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Test sonucu: <strong>{{testInfo.testResult}}</strong></p></class>
                </div>
            </div>
        </div>

        <div class="card border-dark my-3">
            <div class="card-header text-dark">
                <h5>Devreye alma bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row">
                    <class class="col"><p>Devreya alan: <strong>{{commissioningInfo.commissioner}}</strong></p></class>
                    <class class="col"><p>Devrey alma tarihi: <strong>{{commissioningInfo.commissionDate}}</strong></p></class>
                    <class class="col"><p>İletkenlik: <strong>{{commissioningInfo.conductivity}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Son kullanıcı: <strong>{{commissioningInfo.enduser}}</strong></p></class>
                    <class class="col"><p>Adres: <strong>{{commissioningInfo.address}}</strong></p></class>
                    <div class="w-100"></div>
                    <class class="col"><p>Notlar: <strong>{{commissioningInfo.notes}}</strong></p></class>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: "lsdView",
    data: function(){
       return {
            id: 1,
            company: "Ersel Ağır makina A.Ş.",
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
                motor: "0.55kw deg",
                vfd:    "CFW10 2.6A",
                gearbox: "DSV",
                contactor: "HOMA 1600A",
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
       };
    }
}
</script>

<style>

</style>
