<script setup>
import options from '../utils/options.json'
import { ref } from 'vue'
const mail = useMail()

const fullName = ref('');
const phoneNumber = ref('');
const email = ref('')
const service = ref('')
const msg = ref('')
const isSending = ref(false)
const isSend = ref('')

const handleSubmit = async (e) => {
    e.preventDefault();
    if (!fullName.value && !phoneNumber.value && !email.value && !service.value) {
        alert("Enter all details")
        return;
    }
    isSending.value = true
    const msgs = await mail.send({
        from: `"Web service request" <${process.env.EMAIL_SENDER}>`,
        subject: `Service request - ${fullName.value}`,
        html: `<div> 
            <p>Full name: ${fullName.value}</p>
            <p>Phone Number: ${phoneNumber.value}</p>
            <p>Email: ${email.value}</p>
            <p>Service: ${service.value}</p>
            <p>${msg.value}</p>
            </div>`,
    })

    isSending.value = false
    alert("Message sent" + msgs)
}
</script>

<template>
    <div class="min-h-screen w-full p-8 text-black light-blue" id="Contact">
        <h2 class="font-bold text-3xl text-center">Contact Us</h2>
        <div class="w-full min-h-full flex items-center justify-center mt-6">
            <div class="bg-white h-3/4 lg:w-1/2 rounded-md flex items-center justify-center form-card">
                <form class="w-full flex flex-col items-center justify-center py-4">
                    <input type="text" @change="(e) => fullName = e.target.value" name="fullName"
                        placeholder="Full name">
                    <br>
                    <input type="tel" @change="(e) => phoneNumber = e.target.value" name="phoneNumber"
                        placeholder="Phone number"> <br>
                    <input type="email" @change="(e) => email = e.target.value" name="email" placeholder="Email"> <br>
                    <select name="service" @change="(e) => service = e.target.value">
                        <option selected disabled>Service type</option>
                        <option v-for="opt of options" :key="opt" @change="(e) => opt">{{ opt }}</option>
                    </select> <br>
                    <textarea @change="(e) => msg = e.target.value" name="msg" placeholder="message" rows="5"
                        cols="10"></textarea>
                    <button :disabled="isSending" class="text-white font-bold mt-6" @click="(e) => handleSubmit(e)">{{
                        isSending ? "Loading" : "Submit" }}</button>
                </form>
            </div>
        </div>
    </div>

</template>
<style scoped>
input,
select,
textarea {
    width: 90%;
    background-color: white;
    outline: none;
    border: 2px #cccc solid;
    border-radius: 10px;
    padding: 5px 10px;
    margin-bottom: 0.25rem;
}

@media (max-width: 1242px) {
    .form-card {
        width: 70%;
    }
}

@media (max-width: 600px) {
    .form-card {
        width: 100%;
    }
}
</style>