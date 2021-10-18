<template>
  <div>
        <div class="list-group" v-for="hospital in hospitals">
            <a href="#" class="list-group-item list-group-item-action">@{{ hospital.name }}</a>
        </div>
  </div>
</template>
<!--Read from Laravel Database-->
<script>
export default {
    data() {
        return {
            hospitals: []
        }
    },
    created() {
        axios.get('127.0.0.1:90/api/hospitals')
            .then(response => {
                this.hospitals = response.data
            })
            .catch(function (error) {
                console.log(error);
            })
    }
}


</script>

<style>

</style>