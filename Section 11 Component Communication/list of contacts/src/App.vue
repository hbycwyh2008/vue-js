<template>
  <div class="container justify-content-center align-items-center">
    <div class="row align-items-center">
      <div class="col-12">
        <h2 class="mb-3">{{ msg }}</h2>
      <div class="row">
        <div class="col-12" v-for="contact in contacts" :key="contact.name">
          <Contact
            :name="contact.name"
            :phone="contact.phone"
            :ownerName="contact.ownerName"
            :email="contact.email"
            :isFavorite="contact.isFavorite"
          />
        </div>
      </div>
      </div>
      
    </div>
  </div>
</template>


<script setup>
import { reactive } from 'vue';
import Contact from './components/Contact.vue';

const msg = 'Hello Vue';
const contactsOwner = "Vue";
const contacts = reactive([
  {
    name: 'John',
    phone: '123-456-7890',
    ownerName: contactsOwner,
    isFavorite: false
  },
  {
    name: 'Jane',
    phone: '987-654-3210',
    ownerName: contactsOwner,
    isFavorite: true
  },
  {
    name: 'Bob',
    phone: '555-555-5555',
    ownerName: contactsOwner,
    isFavorite: false
  }
]);
</script>