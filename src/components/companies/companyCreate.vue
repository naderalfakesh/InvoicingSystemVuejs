<template>
    <div>
        <div class="card">
            <div class="card-body">
                <div class="row">
                    <div class="col">
                        <h5>İsim</h5>
                        <p><input v-model="companyCreate.name" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Tip</h5>
                        <p><input v-model="companyCreate.type" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Email</h5>
                        <p><input v-model="companyCreate.email" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Website</h5>
                        <p><input v-model="companyCreate.website" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Telefon</h5>
                        <p><input v-model="companyCreate.phone" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Fax</h5>
                        <p><input v-model="companyCreate.fax" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Vergi dairesi</h5>
                        <p><input v-model="companyCreate.taxAdmin" type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5>Vergi Numarası</h5>
                        <p><input v-model="companyCreate.taxNumber" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5>Adres</h5>
                        <p><input v-model="companyCreate.address" type="text" class="form-control"></p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'companyCreate',
    props: ['company'],
    data: function(){
        return{
            companyCreate:{
                id: null,
                name: "",
                type: "",
                email: "",
                website: "",
                phone: "",
                fax: "",
                taxAdmin:"",
                taxNumber:"",
                address:"",
            }
        };
    },
    created: function(){
        if(this.company != null){
            this.companyCreate = this.company
        }
    }
}
</script>

<style>

</style>
