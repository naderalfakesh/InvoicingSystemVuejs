<template>
    <div>
        <button @click="productCreate()" class="btn btn-dark" >Yeni ürün kaydet </button>
        <table class="table">
            <thead>
                <th scope="col">#</th>
                <th scope="col">Ürün tipi</th>
                <th scope="col">ürün kodü</th>
                <th scope="col">seri numarası</th>
                <th scope="col">Genel bilgi</th>
                <th scope="col">Aksyon</th>
            </thead>
            <tbody>
                <tr v-for="(product,index) in products" v-bind:key="index" >
                    <td>{{index+1}}</td>
                    <td>{{product.type}}</td>
                    <td>{{product.materialNumber}}</td>
                    <td>{{product.serialNumber}}</td>
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
                    type: "type 1",
                    materialNumber: "Material 1",
                    serialNumber: "Serial 1",
                    attributes: {
                        brand: "Brand 1", 
                        power: 55,
                        speed: 1000,
                    }
                },    
                {
                    id: 2,
                    type: "type 2",
                    materialNumber: "Material 2",
                    serialNumber: "Serial 2",
                    attributes: {
                        brand: "Brand 2", 
                        power: 45,
                        speed: 1500,
                    }
                },    
                {
                    id: 3,
                    type: "type 3",
                    materialNumber: "Material 3",
                    serialNumber: "Serial 3",
                    attributes: {
                        brand: "Brand 3", 
                        power: 75,
                        speed: 3000,
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
            let entries= Object.entries(this.products[index].attributes)
            let attr=""
            for(let entry of entries){
                attr= attr + entry[0] + ": " + entry[1] + ", "
            }
            return attr
        }
    },
  

}
</script>

<style>

</style>
