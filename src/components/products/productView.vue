<template>
    <div>
        <div class="card">
            <div class="card-body">
                <div class="row" >
                    <div class="col">
                        <h5>Ürün tipi:</h5>
                        <p>{{product.type}}</p>
                    </div>
                    <div class="col">
                        <h5>Ürün Kodu:</h5>
                        <p>{{product.type}}</p>
                    </div>
                </div>
                <div class="row" >
                    <div class="col">
                        <h5>Seri numarası:</h5>
                        <p>{{product.serialNumber}}</p>
                    </div>
                    <div class="col">
                        <h5>Ürün özelikleri:</h5>
                        <ul>
                            <li v-for="(attr,index) in detailedAttributes()" v-bind:key="index">
                               <b> {{attr[0].toUpperCase()}}: </b> {{attr[1]}}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "productView",
    props: ["product"],
    data: function(){
        return {    id: 3,
                    type: "type 3",
                    materialNumber: "Material 3",
                    serialNumber: "Serial 3",
                    attributes: {
                        brand: "Brand 3", 
                        power: 75,
                        speed: 3000,
                        }
        };
    },
    methods:{
        detailedAttributes: function(){
            return Object.entries(this.product.attributes);
        }

    }

}
</script>

<style>

</style>
