<template>
  <div class="container justify-content-center align-items-center">

    <div class="row align-items-center">
      <div class="col-12">
        <h2 class="mb-3">{{ msg }}</h2>
        Contact Owner Name : <input v-model="contactsOwner" />
      <div class="row">
        <div class="col-12" v-for="contact in contacts" :key="contact.name">
          <Contact
            :name="contact.name"
            :phone="contact.phone"
            :ownerName="contactsOwner"
            :email="contact.email"
            :isFavorite="contact.isFavorite"
            @update-favorite="contact.isFavorite = onUpdated($event,contact.phone)"
          />
        </div>
      </div>
      </div>
      
    </div>
  </div>
</template>


<script setup>
import { ref,reactive, onUpdated } from 'vue';
import Contact from './components/Contact.vue';

const msg = 'Hello Vue';
const contactsOwner = ref("Vue");
const contacts = reactive([
  {
    name: 'John',
    phone: '123-456-7890',
    isFavorite: false
  },
  {
    name: 'Jane',
    phone: '987-654-3210',
    isFavorite: true
  },
  {
    name: 'Bob',
    phone: '555-555-5555',
    isFavorite: false
  }
]);

function onUpdated(oldValues, phoneFromParent) {
  return !oldValues[0];
}
</script>