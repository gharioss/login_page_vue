<template>
  <v-row justify="center">
    <v-col cols="4">
      <v-card>
        <v-card-item>
          
        <v-card-title class="text-center">Login Here</v-card-title>
          <v-form @submit.prevent="submit">
            <v-text-field
                prepend-inner-icon="mdi-mail"
                variant="underlined"
                v-model="form.email"
                label="Email"
            ></v-text-field>

            <v-text-field
                type="password"
                prepend-inner-icon="mdi-key"
                variant="underlined"
                v-model="form.password"
                label="Password"
            ></v-text-field>

            <v-checkbox
                v-model="form.remember"
                color="primary"
                label="Remember me"
                value="red"
                hide-details
              ></v-checkbox>

            <v-btn color="primary" class="mt-2" type="submit" block>Submit</v-btn>
          </v-form>
        </v-card-item>
        <div class="mx-4">
          <v-btn block to="/register">Register</v-btn>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

  <script setup lang="ts">
    import { ref } from 'vue';

    const form = ref({
        email: '',
        password: '',
        remember: false,
    })

    function submit() {
        alert(JSON.stringify(form.value))
    }
  </script>