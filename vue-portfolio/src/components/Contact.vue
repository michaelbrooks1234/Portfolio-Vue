<template>
  <v-container>
    <v-form v-model="valid">
      <v-container>
        <v-row class="form-container">
          <div class="secondary-form-container">
            <v-list-item
              title="Contact Me!"
              subtitle="Send me a silly message or a serious inquiry and I will get back to you"
              class="px-0 py-4"
            ></v-list-item>
            <v-text-field
              class="text-field-email pb-2"
              prepend-inner-icon="mdi-email-outline"
              placeholder="Enter your email!"
              :rules="emailRules"
              v-model="email"
            >
            </v-text-field>
            <v-textarea
              no-resize
              prepend-inner-icon="mdi-pencil"
              placeholder="Enter the message you would like to send!"
              class="text-field-message pb-2"
              :rules="messageRules"
              v-model="msg"
            >
            </v-textarea>
            <v-btn
              size="large"
              width="120px"
              @click="sendEmail()"
            >
              <span class="px-2">Send!</span>
              <v-icon
                class="mt-1"
              >
                mdi-email-fast-outline
              </v-icon>
            </v-btn>
          </div>
        </v-row>
      </v-container>
    </v-form>
    <v-snackbar
      v-model="alertOpen"
      :timeout="2500"
      :color="alertType == 'success' ? 'green' : 'red'"
    >
      {{ alertMsg }}
    </v-snackbar>
  </v-container>
</template>
<script lang="ts">
export default {
  data() {
    return {
      alertOpen: false,
      alertMsg: '',
      alertType: 'success',
      email: '',
      emailRules: [
        (v:string) => {
          if (!this.validateEmail()) {
            return 'Email not valid';
          }
          return true;
        }
      ],
      msg: '',
      messageRules: [
        (v:string) => {
          if (v.length === 0) {
            return 'please say something!!!';
          }
          return true;
        }
      ],
      valid: false,
    }
  },
  methods: {
    validateEmail() {
      if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email)) {
        return true;
      }
      return false;
    },
    formValidationFailure() {
      this.alertType = 'error';
      this.alertMsg = 'Email not sent!!';
      this.alertOpen = true;
    },
    emailSuccess() {
      this.alertType = 'success';
      this.alertMsg = 'Email sent!!';
      this.alertOpen = true;
    },
    async sendEmail() {
      if (this.msg.length === 0 || !this.validateEmail()) {
        this.formValidationFailure();
        return;
      }
      const formData = {
        email: this.email,
        message: this.msg
      };
      await fetch('https://formspree.io/f/xanyyeay', {
        method: 'POST',
        body: JSON.stringify(formData),
        headers: {
          'Accept': 'application/json'
        }
      });
      this.emailSuccess();
    }
  }
}
</script>
<style lang="scss" scoped>

.form-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 80vh;
}

.text-field-email {
  width: 25vw;
}

.text-field-message {
  width: 50vw;
}

.secondary-form-container {
  width: 50%;
  height: 40%;
}

@media only screen and (max-width: 700px) {
  .text-field-email {
    width: 70vw;
  }

  .text-field-message {
    width: 70vw;
  }

  .secondary-form-container {
    width: 80%;
    height: 40%;
  }
}
</style>