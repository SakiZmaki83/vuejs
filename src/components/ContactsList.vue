<template>
  <div>

    <form @submit.prevent="addContact">
        <label>First Name</label>
        <input v-model="newContact.firstName" type="text" placeholder="First Name"/>

        <label>Last Name</label>
        <input v-model="newContact.lastName" type="text" placeholder="Last Name"/>

        <label>Email</label>
        <input v-model="newContact.email" type="email" placeholder="Email"/>

        <button type="submit">Add Contact</button>

    </form>

    


      <table>
    
        <thead>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Email</th>
    </thead>
        <tbody>
      <tr v-for="(contact, key) in contacts" :key="key">
          <td>{{ contact.firstName}}</td>
          <td>{{ contact.lastName}}</td>
          <td>{{ contact.email}}</td>
      </tr>
        </tbody>
      </table>
  </div>
</template>
 

<script>
export default {
  name: 'ContactsList',
  data() {
    return {
      contacts: [
        {firstName: 'John', lastName: 'Doe', email: 'john@doe.com'},
        {firstName: 'Mike', lastName: 'Dane', email: 'mike@dane.com'},
        {firstName: 'Steve', lastName: 'Kolin', email: 'steve@kolin.com'}
      ],

      newContact: {
        firstName: '',
        lastName: '',
        email: ''
      }
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
    }
  }
}
</script>

