<template>
    <form @submit.prevent="handleSubmit">
        <h3>dodaj novi projekt</h3>
        <label>Title:</label>
        <input type="text" v-model="title" required>
        <label> Details:</label>
        <textarea  v-model="details"  required></textarea>
        <button>Add project</button>

    </form>

</template>
  
<script>
export default{
    data(){
        return {
            title: "",
            details: ""
        }
    },
    methods:{
        handleSubmit(){
            let project = {
                title:this.title,
                details:this.details,
                complete: false
            }
            fetch("https://fm-lab6-jsonserver.onrender.com/projects",
            {
                method: "POST",
                headers: {"Content-Type": "application/json"},
                body: JSON.stringify(project)
            })
            .then(() => {
                this.$router.push("/")
            })
            .catch((err) => console.log(err))
        }

    }

}

</script>

<style scoped>
    h3 {
        color: blueviolet;
    }

    form {
        background: white;
        padding: 20px;
        border-radius: 10px;
    }
    label{
        display: block;
        color: grey;
        text-transform: uppercase;
        font-size: 14px;
        font-weight: bold;
        letter-spacing: 1px;
        margin: 20px 0 10px 0;
    }
    input{
        padding: 10px;
        border: 0;
        border-bottom: 1px solid #ddd;
        width: 100%;
        box-sizing: border-box;
    }
    textarea {
        border: 1px solid #ddd;
        padding:  10px;
        width: 100%;
        box-sizing: border-box;
    }
    form button {
        display: block;
        margin: 20px auto 0;
        background: green;
        color: white;
        padding: 10px;
        border: 0;
        border-radius: 6px;
        font-size: 16px;
    }


</style>
  