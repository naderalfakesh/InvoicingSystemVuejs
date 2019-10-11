<template>
    <div>
        <button @click="productCreate()" class="btn btn-dark btn-sm" >Yeni ürün kaydet </button>
        <table class="table table-sm">
            <thead>
                <th scope="col">#</th>
                <th scope="col">ürün kodü</th>
                <th scope="col">seri numarası</th>
                <th scope="col">Ürün tipi</th>
                <th scope="col">Genel bilgi</th>
                <th scope="col">Aksyon</th>
            </thead>
            <tbody>
                <tr v-for="(product,index) in products" v-bind:key="index" >
                    <td>{{index+1}}</td>
                    <td>{{product.materialNumber}}</td>
                    <td>{{product.serialNumber}}</td>
                    <td>{{product.type.toUpperCase()}}</td>
                    <td>{{detailedAttributes(index)}}</td>
                    <td>
                        <button @click="productShow(index)" class="btn btn-sm btn-primary" title="İncele">İ</button>
                        <button @click="productEdit(index)" class="btn btn-sm btn-info" title="Düzelt">D</button>
                        <button @click="productDelete(index)" class="btn btn-sm btn-danger" title="Sil">S</button>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: "productIndex",
    data: function(){
        return {
            products: [
                {
                    id: 1,
                    type: "motor",
                    materialNumber: "Material 1",
                    serialNumber: "Serial 1",
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
                    }
                },    
                {
                    id: 2,
                    type: "vfd",
                    materialNumber: "Material 2",
                    serialNumber: "Serial 2",
                    vfd: {
                        brand: "WEG",
                        series: "CFW09",
                        type: "softstarter",
                        power: 315,
                        current: 600,
                        voltage: 400,
                        frame: 10,
                    }
                },    
                {
                    id: 3,
                    type: "lsd",
                    materialNumber: "Material 3",
                    serialNumber: "Serial 3",
                    lsd: {
                        brand: "degdrive",
                        series: "LSDEmini",
                        productionDate: "01-02-2019", 
                        motorpower: 630,
                        rotorcurrent: 687,
                        rotorvoltage: 1230
                    }
                },    
                  
            ]
            ,
        };
    },
    methods:{
        productCreate: function(){
            this.$router.push({name: "productCreate" , params: {product: null} })
        },
        productShow: function(index){
            this.$router.push({name: "productView" , params: {product: this.products[index]} })
        },
        productEdit: function(index){
            this.$router.push({name: "productEdit" , params: {product: this.products[index]} })
        },
        productDelete: function(index){
            alert("Are you sure you want to delete this" + index) 
        },
        detailedAttributes: function(index){
            let attr="";
            if(this.products[index].type== "motor"){
                let mot=this.products[index].motor
                attr= `${mot.brand} ${mot.series} ${mot.power}kW ${mot.pole}K ${mot.frame}gövde ${mot.frequency}hz ${mot.type} `
            }
            else if(this.products[index].type== "vfd"){
                let vfd=this.products[index].vfd
                attr=`${vfd.brand} ${vfd.series} ${vfd.type} ${vfd.current}A ${vfd.power}kW`
            }
            else if(this.products[index].type== "lsd"){
                let lsd=this.products[index].lsd
                attr=`${lsd.brand} ${lsd.series} ${lsd.motorpower}kW  ${lsd.rotorcurrent}A ${lsd.rotorvoltage}V ${lsd.productionDate}`
            }
            else {
                attr="Wrong product type"
            }
            return attr
        }
    },
    
  

}
</script>

<style>

</style>
