<!--New Hospital form-->
<template>
    <div>
        <form>
            <div class="form-group">
                <label>Name of the hospital:</label>
                <input type="text" v-model="name" placeholder="Enter name of the hospital" class="form-control" >
            </div>
            <div class="form-group">
            <label>Code of the hospital:</label>
            <input type="text" v-model="code" placeholder="Enter code of the hospital" class="form-control">
            </div>
            <div class="form-group">
            <label>Hospital type:</label>
            <select v-model="type" class="form-control">
                <option value="free">Free</option>
                <option value="premium">Premium</option>
            </select>
            </div>
        </form>
        <button type="button" class="btn btn-primary" @click="addHospital">Add Hospital</button>
    </div>
</template>
<!--Export form into Laravel databse-->
<script>
export default {
    data() {
        return {
            name: '',
            code: '',
            type: 'free'
        }
    }, methods: {
        addHospital() {
            axios.post('127.0.0.1:90/api/hospitals', {
                name: this.name,
                code: this.code,
                type: this.type
            })
            .then(response => {
                console.log(response.data);
            })
            .catch(error => {
                console.log(error.response.data);
            });
        }
    }
}
</script>

<style>
</style>