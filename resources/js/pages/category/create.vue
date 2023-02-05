<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-12">
                <div class="card ">
                    <div class="card-header d-flex justify-content-betweet align-items-center">
                        <h4>Product Category</h4>
                        <router-link :to="{name: 'category-list'}" class="btn btn-primary btn-sm"> Category List</router-link>
                    </div>
                    <div class="card-body">
                        <div class="row">
                            <form @submit.prevent="submitData">
                                <div class="col-md-6 offset-md-3">
                                    <h1 class="text-center">Add Category</h1>
                                    <div class="form-group">
                                        <label for="">Name</label>
                                        <input type="text" v-model="categoryName" name="name" class="form-control">
                                    </div>
                                    <button type="submit" class="btn btn-primary mt-2">Submit</button>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            categoryName: '',
        }
    },
    methods: {
        submitData() {
            axios.post('api/category', { name: this.categoryName }).then(response => {
                console.log(response);
            });
        }
    }
}
</script>
