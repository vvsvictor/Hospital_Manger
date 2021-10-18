<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">Hospital Manager</div>

                    <div class="card-body">
                        <div id = "showh">
                            List of hospitals
                            <Hospitallist/>
                        </div>
                        <div id = "addh">
                            Add Hospital
                            <Form/>
                        </div>
                    </div>
                    
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Form from './Form.vue'
import Hospitallist from './Hospitallist.vue'
    export default {
        mounted() {
            console.log('Component mounted.')
        },components: {
            Form,
            Hospitallist
        }
    }

</script>
<style>
@import url("https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css");
</style>