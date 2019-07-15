<template>
    <div>
        <div class="card">
            <div class="card-body">
                <div class="row">
                    <div class="col">
                        <h5></h5>
                        <p><input type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5></h5>
                        <p><input v-model="companycreate.name" type="text" class="form-control"></p>
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <h5></h5>
                        <p><input type="text" class="form-control"></p>
                    </div>
                    <div class="col">
                        <h5></h5>
                        <p><input type="text" class="form-control"></p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
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
                taxAdmin:"",
                taxNumber:"",
                address:"",
            }
        };
    }
}
</script>

<style>

</style>
