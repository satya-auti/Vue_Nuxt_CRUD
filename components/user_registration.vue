<template>
    <div>
        <div class="flex justify-center">
            <form @submit="submitUserForm" method="post">

            
                <h1 class="text-center text-3xl font-bold text-cyan-800 mt-16">User Registration</h1>
                <table class="mt-5">
                    <tr>
                        <td>
                            <label for="firstName">First Name</label>
                        </td>
                        <td>
                            <input v-model="userData.firstName" class="pl-5 ring-2 focus:ring-2 focus:ring-lime-600 rounded-lg m-3" type="text" name="firstName" id="firstName" placeholder="First Name">
                        </td>
                    </tr>

                    <tr>
                        <td>
                            <label class="font-bold italic" for="lastName"> Last Name </label>
                        </td>
                        <td>
                            <input class="pl-5 ring-2 rounded-lg m-3" v-model="userData.lastName" type="text" id="lastName" name="lastName" placeholder="Last Name">
                        </td>
                    </tr>

                    <tr>
                        <td>
                            <label for="email"> Email </label>
                        </td>
                        <td>
                            <input class="pl-5 ring-2 rounded-lg m-3" v-model="userData.email" type="email" name="email" id="email" placeholder="Email">
                        </td>
                    </tr>

                    <tr>
                        <td>
                            <label for="dob">Date of Birth</label>
                        </td>
                        <td>
                            <input class="pl-5 ring-2 rounded-lg m-3" v-model="userData.dob" type="date" name="dob" id="dob" placeholder="MM/DD/YYYY">
                        </td>
                    </tr>

                    <tr>
                        <td>

                        </td>
                        <td>
                            
                        </td>
                    </tr>
                    <!-- Submit & Reset Buttons -->
                    <tr>
                        <td>

                        </td>
                        <td>
                            <button class="bg-blue-600 hover:bg-blue-800 text-white px-2 p-1 mr-2 rounded-xl" type="submit">Submit</button>
                            <button class="bg-blue-600 hover:bg-red-600 text-white px-2 py-1 mr-2 rounded-xl" type="reset">Reset</button>
                        </td>
                    </tr>
                </table>
            </form>
        </div>

        <hr class=" m-2 border-4 border-orange-600">

        <!-- <button @click="showData" type="button" class="bg-blue-600 hover:bg-red-600 text-white px-2 py-1 mr-2 rounded-xl" >Show User Data</button> -->

        <!-- Table code to show data -->
        <!-- <div v-if="show"> -->
        <div>
            <table class="border-2 border-black">
                <tr >
                    <th class="border-2 border-black">
                        First Name
                    </th>
                    <th class="border-2 border-black">
                        Last Name
                    </th>
                    <th class="border-2 border-black">
                        Email
                    </th>
                    <th class="border-2 border-black">
                        Date of Birth
                    </th>
                    <th colspan="2" class="border-2 border-black">
                        Action
                    </th>
                </tr>
                <tr v-for="user in allUserData" :key="user">
                    <td class="border-2 border-black">
                        {{user.firstName}}
                    </td>
                    <td class="border-2 border-black">
                        {{user.lastName}}
                    </td>
                    <td class="border-2 border-black">
                        {{user.email}}
                    </td>
                    <td class="border-2 border-black">
                        {{user.dob}}
                    </td>
                    <td class="border-2 border-black">
                        <button class="bg-blue-600 hover:bg-blue-700 text-white px-2 py-1 mr-2 rounded-xl" type="button">Edit</button>
                    </td>
                    <td class="border-2 border-black">
                        <button class="bg-red-600 hover:bg-red-700 text-white px-2 py-1 mr-2 rounded-xl" type="button">Delete</button>
                    </td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>




export default {
    data(){
        return{
            allUserData : [],
            // show : false,
            userData : {
                firstName : '',
                lastName : '',
                email : '',
                dob : '',
            },
        }
    },
    methods: {
        submitUserForm(event){
            event.preventDefault();
            console.log(this.userData);
            this.allUserData.push(this.userData);
            this.userData = {firstName:'', lastName:'', email:'', dob:''};
            console.log(" User Form Values", this.allUserData);
        },
        showData(){
            //  this.show = true;
            // this.allUserData;
            // this.allUserData.push(this.userData);
            // console.log(" User Form Values", this.allUserData);
        },
    }
}

</script>

<style scoped>

</style>
