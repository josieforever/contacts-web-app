<template>
    <form @submit.prevent="" id="phone-add-contact">
        <div id="utility-container">
            <i class="fa-sharp fa-solid fa-plus" @click="plus" ></i>
            <i class="fa-sharp fa-solid fa-magnifying-glass"></i>
        </div>
        <div id="input-container" v-if="toggleAddContact">
            <div id="phone-add-contact-button"> <i class="fa-solid fa-user"></i>   <input type="text" v-model="enteredName" placeholder="  Name" required /> </div>
            <div id="phone-add-contact-button"> <i class="fa-solid fa-user-tag"></i> <input type="text" v-model="enteredUsername" placeholder="  Username" required /> </div>
            <div id="phone-add-contact-button"> <i class="fa-solid fa-phone"   ></i> <input type="tel" v-model="enteredPhone" placeholder="  Phone" required /> </div>
            <div id="phone-add-contact-button"> <i class="fa-solid fa-envelope"></i> <input type="email" v-model="enteredEmail" placeholder="  Email" required /> </div>
            <div id="action-buttons"> <span id="cancel" @click="cancel">cancel</span> <span id="save" @click="submitData()">Save</span> </div>  
        </div>    
    </form>
</template>

<script>
export default {
    name: 'AddNewContact',
    emits: ['addContact'],
    data() {
        return {
            enteredName:'', enteredUsername:'', enteredPhone:'', enteredEmail:'', toggleAddContact: false
        }
    },
    methods: {
        submitData() {
            if (this.enteredName === ''|| this.enteredUsername === ''|| this.enteredPhone === ''|| this.enteredEmail === '') {
                alert('This is a required field')
            } else {
            this.$emit('addcontact', this.enteredName, this.enteredUsername, this.enteredPhone, this.enteredEmail)
            this.enteredName=''; this.enteredUsername=''; this.enteredPhone=''; this.enteredEmail='';
            this.toggleAddContact = false
            }
        },
        plus() {
            this.toggleAddContact = true
        },
        cancel() {
            this.toggleAddContact = false
            this.enteredName=''; this.enteredUsername=''; this.enteredPhone=''; this.enteredEmail='';
        }
    }
}


</script>

<style scoped>
/* #phone-add-container {
  height: 50px;
  width: 500px;
  border-radius: 25px;
  margin: 10px 0 10px 0;
  background-color: red;
  display: flex;

} */

#phone-add-contact {
    width: 500px;
    min-height: 0px;
    border-radius: 25px;
    background-color: black;
    margin: 5px 0 5px 0;
    padding: 0.2rem;
    color: white;
    display: flex;
    flex-direction: column;
    align-items: center;
}

#utility-container {
    width: 480px;
    height: 50px;
    border-radius: 25px;
    color: white;
    font-size: 2rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr;
    margin: 5px 0 5px 0;
}

#input-container {
    width: 490px;
    min-height: 0px;
    border-radius: 25px;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.fa-plus, .fa-magnifying-glass{
    display: grid;
    place-content: center;
}
.fa-plus:active, .fa-magnifying-glass:active {
  color: rgb(255, 140, 0);
}

input {
    height: 50px;
    width: 430px;
    border-radius: 25px;
    font-size: 1.2rem;
    color: white;
    background-color: rgba(255, 255, 255, 0.1);
    border: 0;
    padding: 0.8rem;
    /* text-decoration-color: aliceblue; */
}

input:active ,input:focus {
    outline-color: rgba(255, 166, 0, 0.814);
    border: 0;
}



#phone-add-contact-button {
    width: 480px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    margin-top: 3px;
}

#action-buttons {
    width: 470px; 
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
}

#cancel, #save {
    padding: 0.5px 5px 0.5px 5px;
    border-radius: 15px;
    color: white;
    margin: 3px 0px;
    transition: 0.3s; 
}

#cancel:active , #save:active, #cancel:hover , #save:hover  {
    background-color: rgb(255, 140, 0);
    cursor: pointer;
}

#phone-add-contact {
    color: rgba(255, 166, 0, 0.814);
}
</style>