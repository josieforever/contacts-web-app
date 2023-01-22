<template>
    <div id="outer-container" @click="toggleDropDown()" >
        <div id="inner-container-top"> 
            <div id="display-letter" :style="displayLetterColor">{{ displayLetter }}</div>
            <div id="contact-name">{{ name }}</div>
        </div>
        <div id="inner-container-bottom" v-if="dropDown" >Mobile
            {{ phone }}
            <div id="actions">
                <i class="fa-sharp fa-solid fa-phone" ></i>
                <i class="fa-sharp fa-solid fa-message"></i>
                <i class="fa-sharp fa-solid fa-video"></i>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'PhoneBody',
    props: ['id','name','username','phone','email', ' isClicked'],
    data() {
        return {
            dropDown: this.isClicked
        }
    },
    methods: {
        toggleDropDown() {
            this.dropDown = !this.dropDown
        }
    },
    computed: {
        displayLetter() {
            return this.name.charAt(0).toUpperCase() 
        },
        displayLetterColor() {
            let color = Math.floor((Math.random() * 7) + 1)
            if (color === 1) {
                return {backgroundColor: 'lightgreen'}
            } else if (color === 2) {
                return {backgroundColor: 'pink'}
            } else if (color === 3) {
                return {backgroundColor: 'lightskyblue'}
            } else if (color === 4) {
                return {backgroundColor: 'lightcoral'}
            } else if (color === 5) {
                return {backgroundColor: 'lightgoldenrodyellow'}
            } else if (color === 6) {
                return {backgroundColor: 'magenta'}
            } else if (color === 7) {
                return {backgroundColor: 'rebeccapurple'}
            } else if (color === 8) {
                return {backgroundColor: 'lightred'}
            } else {
                return {backgroundColor: 'indigo'}
            }
        }
    }
}
  
</script>
  
<style scoped>

#outer-container {
    width: 450px;
    min-height: 90px;
    margin-top: 5px;
    background-color: rgba(255, 255, 255, 0.15);
    border-radius: 25px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 5px;
    color: white;
    font-size:1.2rem;

}

#inner-container-top {
    height: 50px;
    width: 440px;
    border-radius: 25px;
    background-color: transparent;
    display: flex;
    flex-direction: row;
    align-items: center;
}

#display-letter {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    display: grid;
    place-content: center;
    background-color: darkgoldenrod;
    margin-left: 10px;
}

#contact-name {
    margin-left: 10px;
    color: white;
}

#actions {
    height: 50px;
    width: 440px;
    border-radius: 25px;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
}

#inner-container-bottom {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

#call, #message, #video {
    height: 40px;
    width: 40px;
    border-radius: 50%;
    background-color: rgb(11, 184, 34);
}

.fa-phone {
    color: white;
    background-color: green;
    padding: 8px;
    border-radius: 50%
}

.fa-message {
    color: white;
    background-color: dodgerblue;
    padding: 8px;
    border-radius: 50%
}
.fa-video {
    color: white;
    background-color: teal;
    padding: 8px;
    border-radius: 50%
}


</style>