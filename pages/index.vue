<template>
    <!-- <div>
        <div>
            <H1>User Registration</H1>
            <table>
                <tr>
                    <td>
                        <label for="firstName">First Name</label>
                    </td>
                    <td>
                        <input type="text" name="firstName" id="firstName" placeholder="First Name">
                    </td>
                </tr>

                <tr>
                    <td>
                        <label for="lastName"> Last Name </label>
                    </td>
                    <td>
                        <input type="text" id="lastName" name="lastName" placeholder="Last Name">
                    </td>
                </tr>

                <tr>
                    <td>
                        <label for="email"> Email </label>
                    </td>
                    <td>
                        <input type="email" name="email" id="email" placeholder="Email">
                    </td>
                </tr>

                <tr>
                    <td>

                    </td>
                    <td>
                        
                    </td>
                </tr>

                <tr>
                    <td>

                    </td>
                    <td>
                        
                    </td>
                </tr> -->
                <!-- Submit & Reset Buttons -->
                <!-- <tr>
                    <td>

                    </td>
                    <td>
                        <button type="submit">Submit</button>
                        <button type="reset">Reset</button>
                    </td>
                </tr>
            </table>
        </div>
    </div>-->
    <div>
        <div>
            <!-- <trial></trial> -->
        </div>
        <user-registration></user-registration>
    </div>
</template> 

<script>
import { defineComponent } from '@vue/composition-api'
import user_registration from './user_registration.vue'


definePageMeta({
    components: {
        user_registration,
       
    }
})

export default defineComponent({
    setup() {
        
    },
})
</script>

<style scoped>

</style>
