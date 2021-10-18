<template>

    <div class="container">
        <div class="row">
            <div class=" col-lg-6 mt-5">

                <div class="col-lg-8 mb-2 " @click="name=true">
                        <div class="form-check form-check-inline">
                            <input v-model="select" class="form-check-input" type="radio" name="createMeeting" id="inlineRadio1" value="create">
                            <label class="form-check-label btn btn-secondary  p-2 pt-0" for="inlineRadio1">
                                <img style="width:25px;margin-left:12px" src="https://www.svgrepo.com/show/109574/play.svg" alt="">
                                Creat a Meeting</label>

                        </div>
                </div>
                <div class="input-group m-4" style="width:210px !important" v-if="name">
                    <input v-model="nameMeeting" type="text" class="form-control" placeholder="Meeting name" aria-label="Recipient's username" aria-describedby="button-addon2">
                </div>
                <div class="col-lg-8 mb-2">
                        <div class="form-check form-check-inline"  @click="name=false">
                                <input v-model="select" class="form-check-input" type="radio" name="joinMeeting" id="inlineRadio2" value="join">
                                <label class="form-check-label btn btn-secondary p-1 pt-0" for="inlineRadio2">
                                <img style="width:25px" src=" https://www.svgrepo.com/show/78994/link.svg" alt="">
                                    Join a Meeting</label>
                        </div>
                </div>

                <div class="btn btn-success m-4 " @click="sub" :href="route('chatRoomCreate')" style="height:50px;font-size:22px">
                    <img style="width:25px" src=" https://www.svgrepo.com/show/46118/next.svg" alt="">
                                   Next
                </div>

                <!-- <div class="col-lg-8">
                        <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option3" disabled>
                                <label class="form-check-label btn btn-secondary p-2 pt-0" for="inlineRadio3">3 (disabled)</label>
                        </div>
                </div> -->

            </div>
             <div class="col-lg-6">
                  <img class="w-100" src="https://miro.medium.com/max/1400/0*V81dr5lik43EIsJn" alt="">
             </div>
             </div>



    </div>
</template>
<style scoped>
    a {
        text-decoration: none;
        color:black !important;
    }
    .form-check-input {
        font-size: 20px;
        line-height: 80px;
        margin-top: 15px;
    }
    label {
        display: block;
        width: 220px;
        height: 50px;
        font-size: 20px;
        line-height: 50px;

    }
</style>
<script>
const axios = require('axios').default;
import { defineComponent } from "vue"
import { Head, Link } from '@inertiajs/inertia-vue3';
export default ({
    components: {
    Head,
    Link,
  },

    data() {
        return {
            select:'',
            name:false,
            nameMeeting:''
        }
    },
    methods : {
        sub:function() {
           /*  if(this.select=="create") {
                console.log(2)
            }
            if(this.select=="create") {
                console.log(2)
            } */
            switch (this.select) {
                case 'create' :
                    const headers = {
                                    "Authorization": "Basic MmFjMTc2YjUwMjgxNGU3ZTlhNjBiNmUzNjM0MDQ1OGQ6ZjM1MTA1OGViZGVkNGM4Mzk2ODhiMDUzZDYzNjI5NTI=",
                                    "Accept": "application/json",
                                };
                   axios.post('https://api.agora.io/dev/v1/project', {name: this.name},{ headers })
                            .then(function (response) {
                                console.log(response);
                            })
                            .catch(function (error) {
                                console.log(error);
                            });


                case 'join' :
                    console.log(3);



            }
        }
    }


})
</script>
