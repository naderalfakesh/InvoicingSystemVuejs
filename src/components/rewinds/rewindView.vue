<template>
    <div>
        <div class="card border-primary">
            <div class="card-header text-primary">
                <h5>Motor bilgileri</h5>
            </div>
            <div class="card-body">
                <div class="row">
                    <div class="col"><b>Sarım tarihi</b></div>
                    <div class="col"><b>Firma</b></div>
                    <div class="col"><b>Marka</b></div>
                    <div class="col"><b>Ürün kodu</b></div>
                    <div class="col"><b>Seri numarası</b></div>
                    <div class="col"><b>Güç</b></div>
                    <div class="col"><b>kutup sayısı</b></div>
                    <div class="col"><b>Frekans</b></div>
                </div>
                <div class="row">
                    <div class="col">{{rewindingDate}}</div>
                    <div class="col">{{customer}}</div>
                    <div class="col">{{motor.brand}}</div>
                    <div class="col">{{materialNumber}}</div>
                    <div class="col">{{serialNumber}}</div>
                    <div class="col">{{motor.power}} Kw</div>
                    <div class="col">{{motor.pole}} K</div>
                    <div class="col">{{motor.frequency}} Hz</div>
                </div>
            </div>
        </div>
        <div class="card border-info mt-3">
            <div class="card-header text-info">
               <h5> Sarım bilgileri </h5>
            </div>
            <div class="card-body">
                <div class="row">
                    <div class="col"> </div>
                    <div class="col"><b>Orijinal</b></div>
                    <div class="col"><b>Yeni</b></div>
                    <div class="w-100"></div>
                    <div class="col"><b>Gerilim</b></div>
                    <div class="col">{{actualVoltage}} V</div>
                    <div class="col">{{newVoltage}} V</div>
                    <div class="w-100"></div>
                    <div class="col"><b>Frekans</b></div>
                    <div class="col">{{actualFrequency}} Hz</div>
                    <div class="col">{{newFrequency}} Hz</div>
                    <div class="w-100"></div>
                    <div class="col"><b>Akım</b></div>
                    <div class="col">{{actualCurrent}} A</div>
                    <div class="col">{{newCurrent}} A</div>
                    <div class="w-100"></div>
                    <div class="col"><b>Teller</b></div>
                    <div class="col">{{actualWire[0].quantity}} x {{actualWire[0].guage}}
                        {{actualWire.length >1 ? " & "+actualWire[1].quantity +" x "+ actualWire[1].guage : "" }}
                    </div>
                    <div class="col">{{newWire[0].quantity}} x {{newWire[0].guage}}
                        {{newWire.length >1 ? " & "+newWire[1].quantity +" x "+ newWire[1].guage : "" }}
                    </div>
                    <div class="w-100"></div>
                    <div class="col"><b>Tür sayısı</b></div>
                    <div class="col">{{actualNumberOfTurns}}</div>
                    <div class="col">{{newNumberOfTurns}} </div>
                    <div class="w-100"></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "rewindView",
    data:function(){
        return {
            rewindingDate: "02-01-1991",
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
                frequency: 50,
                effeciency: "IE2",
                frame: 225,
                pole: 6
            },
            actualWire: [
                {
                quantity: 2,
                guage: 1.18,
                section: 0
                },
                {
                quantity: 3,
                guage: 1,
                section: 0
                }
            ],
            actualVoltage: 400,
            actualCurrent: 1,
            actualFrequency: 50,
            actualNumberOfTurns: 15,

            newWire: [
                {
                quantity: 2,
                guage: 0.5,
                section: 0
                },
                {
                quantity: 2,
                guage: 0.5,
                section: 0
                }
            ],
            actualWireSection: 15,
            newVoltage: 400,
            newCurrent: 1,
            newFrequency: 84,
            newNumberOfTurns: 15,
            
        };
    }
}
</script>

<style>

</style>
