<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12" class="my-4">
        <div class="text-h4 mb-3">
          Task 2
        </div>

        <div class="subheading font-weight-regular">
          We want to build a form to record user details.

          <div class="py-3">
            Open the file <code>/src/components/Task2.vue</code> and modify the code below so that:
            <ol class="list-center">
              <li>
                When I press on "save", the user information is saved and the form is cleared.
              </li>
              <li>
                Any saved user is displayed on the right hand side table.
              </li>
            </ol>
            Once completed, proceed to the next task.
          </div>
          <div class="text-caption">
            Note: feel free to edit any of the component properties (data, methods, etc..)
          </div>
        </div>
      </v-col>
    </v-row>

    <!-- EDIT CODE BELOW -->
    <v-row>
      <v-col cols="12" sm="6">

        <v-card @submit="handleSubmit" class="pa-4"> <!-- TODO: handleSubmit function in methods. Define submit object data function(?) -->

         <!-- Add class of submit input or valid input, create model of userInfo on firstName and lastName. Once entered, clear input status (clearStatus). -->
          <v-text-field 
          v-bind:class="submit"
          v-model="userInfo.firstName"
          @focus="userInfo.firstName"
          @keypress="clearStatus"
          label="First Name" />

          <v-text-field 
          v-bind:class="submit"
          v-model="userInfo.lastName"
          @keypress="clearStatus"
          label="Last Name" />
    <!-- @click save user info and clear input. Event handler. -->
          <v-btn color="primary">Save</v-btn>
        </v-card>
      </v-col>
      <v-col cols="12" sm="6">
        <v-data-table
          :headers="[
            {text: 'First Name', value: 'firstName'},
            {text: 'Last Name', value: 'lastName'},
          ]"
          hide-default-footer
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Task2',
    data () {
      return {
        submit: false,
        userInfo: [
          {
            firstName: '',
            lastName:''
          }
        ]
      }
    },
    methods: {
      handleSubmit() {
        // clearStatus input 
        // if firstName || lastName === false, error is true
        // get newUser
        // push newUser to userInfo
        // clearStatus input 
      },
      clearStatus() {
        // clearStatus function while input text field is valid or invalid. 
      }
    },
  }
</script>
