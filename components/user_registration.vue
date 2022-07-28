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
                            <button class="bg-blue-600 hover:bg-blue-800 text-white px-2 p-1 mr-2 rounded-xl" id="submit" type="submit">Submit</button>
                            <button @click="resetForm" class="bg-blue-600 hover:bg-red-600 text-white px-2 py-1 mr-2 rounded-xl" type="reset">Reset</button>
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
                        ID
                    </th>
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
                    <th colspan="2">
                        Action
                    </th>
                </tr>
                <tr v-for="(user, index) in allUserData" :key="user">
                    <td class="border-2 border-black">
                        {{user.id = index + 1}}
                    </td>
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
                        <button @click="onEdit(user.id)" class="bg-blue-600 hover:bg-blue-700 text-white px-2 py-1 mr-2 rounded-xl" type="button">Edit</button>
                    </td>
                    <td class="border-2 border-black">
                        <button  @click="deleteUser(user.id)" class="bg-red-500 hover:bg-red-600 text-white px-2 py-1 mr-2 rounded-xl" type="button">Delete</button>
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
            isEdit: false,
            // index: index + 1,
            allUserData : [],
            // i : 0,
            // show : false,
            userData : {
                id:0,
                firstName : '',
                lastName : '',
                email : '',
                dob : '',
            },
        }
    },
    methods: {
        submitUserForm(event){
            event.preventDefault(event);
            console.log(this.userData);
            this.allUserData.push(this.userData);
            this.userData = {firstName:'', lastName:'', email:'', dob:''};
            console.log(" User Form Values", this.allUserData);
            const myButton = document.getElementById('submit');
            myButton.innerText = 'Submit';
        },
        onEdit(index){
            console.log(this.allUserData[index]);
            // console.log(this.allUserData[this.index]);
            this.userData.firstName = this.allUserData[index-1].firstName;
            this.userData.lastName = this.allUserData[index-1].lastName;
            this.userData.email = this.allUserData[index-1].email;
            this.userData.dob = this.allUserData[index-1].dob;

            const myButton = document.getElementById('submit');
            myButton.innerText = 'Update';
            this.isEdit=true;
            if(isEdit==true){
                this.allUserData[index-1].firstName = this.userData.firstName ;
                this.allUserData[index-1].lastName = this.userData.lastName ;
                this.allUserData[index-1].email = this.userData.email ;
                this.allUserData[index-1].dob = this.userData.dob ;
            }else{
                alert("unable to update");
            }
            // this.submitUserForm();
        },
        deleteUser(index){
            console.log(index-1);
            this. allUserData.splice(index-1, 1);
            const myButton = document.getElementById('submit');
            myButton.innerText = 'Submit';
        },  
        resetForm() {
            console.log("reset call");
            const myButton = document.getElementById('submit');
            myButton.innerText = 'Submit';
            // indexOfEdit=-1;
            this.isEdit=false;
            this.userData = {id:'', firstName:'', lastName:'', email:'', dob:''};
        },
    }
}

</script>

<style scoped>

</style>
