<template>
  <v-container fluid>
    <v-overlay :model-value="isLoading" class="align-center justify-center">
      <v-progress-circular
        v-if="isLoading"
        color="white"
        indeterminate
        ></v-progress-circular>
    </v-overlay>
    <v-row justify="center">
      <v-col cols="4">
        <v-card>
          <v-card-item>
            
          <v-card-title class="text-center">Login Here</v-card-title>
            <v-form @submit.prevent="submit">
              <v-text-field
                  prepend-inner-icon="mdi-mail"
                  v-model="form.email"
                  label="Email"
              ></v-text-field>

              <v-text-field
                  type="password"
                  prepend-inner-icon="mdi-key"
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

              <v-btn color="primary" class="mt-2" type="submit" variant="elevated" block>
                Submit
              </v-btn>
            </v-form>
          </v-card-item>
          <div class="mx-4 mb-4">
            <v-btn block to="/register">Register</v-btn>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

  <script setup lang="ts">
    import { ref } from 'vue';

    const form = ref({
        email: '',
        password: '',
        remember: false,
    })

    const isLoading = ref(false);

    function submit() {
      isLoading.value = true;

      setTimeout(() => {
        isLoading.value = false;
        alert(JSON.stringify(form.value))
      }, 2000);

    }
  </script>