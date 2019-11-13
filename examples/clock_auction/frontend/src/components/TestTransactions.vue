<template>
    <v-container fluid>
        <v-row>
            <v-col cols="12">Test Transactions</v-col>
        </v-row>
        <v-row>
            <v-textarea outlined v-model="transactionName" label="Enter transaction name" value=""></v-textarea>
        </v-row>
        <v-row>
            <v-textarea outlined v-model="args" label="Enter args in JSON format" value="{}"></v-textarea>
        </v-row>
        <v-row>
            <v-col cols="12">
                <div class="d-flex justify-end">
                    <v-btn color="primary" @click="submitTest">Submit Transaction Call</v-btn>
                </div>
            </v-col>
        </v-row>
    </v-container>
</template>
<style scoped>
.my-input.v-input .v-input__slot {
  border: 1px;
  border-color: black
}
</style>
<script>
    //import axios from 'axios';

    export default {
        name: 'TestTrans',
        data () {
            return {
                transactionName: '',
                args: ''
            }
        },
        mounted () {
        },
        methods: {
            submitTest: function () {
                
                this.confirmDialog = false
                alert ("Transaction Name: " + this.transactionName + ", Args: " + this.args)
                //axios.post('http://localhost:3000/submit_transaction', this.transactionName, this.args)
                //.then()
                //.catch(error => {
                //    alert ("error "+ error)
                //    this.errored = true
                //})
                //.finally(() => this.loading = false)
            }
        }
    }
</script>
