<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{switchName()}}</p>
        <p>User Age: {{userAge}}</p>
        <button @click="resetName">Reset Name</button>
        <button @click="resetFn()">Reset Name Function</button>
    </div>
</template>

<script>
    export default {
        //props with validation must String value
        //props with atribute
        //type: Object, Array, String, boolean, etc
        props:{
            myName: {
                type: String,
                required:true
                /*default: function () {
                    return {
                        name: 'Waviq Default value props'
                    }
                }*/
            },
            resetFn:Function,
            userAge: Number
        },
        methods:{
            switchName() {
                return this.myName.split("").reverse().join("");
            },
            resetName() {
                this.myName = 'Waviq Reset Name'
                this.$emit('nameWasReset', this.myName)
            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
