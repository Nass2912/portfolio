<template>
    <main>
        <div class="content">
        CONTACT
        </div>
        <div class="sub-content">
            Feel free to contact me via the form below and I will get back to you as soon as possible 
            <v-form 
              ref="myForm"
              v-model="valid" 
              @submit="onSubmit"
              action="https://formspree.io/f/mvojnawe"
              method="POST"
            >
                <v-container>
                <v-row>
                    <v-col
                    cols="12"
                    md="4"
                    >
                    <v-text-field
                        v-model="firstname"
                        name="firstname"
                        :rules="nameRules"
                        :counter="10"
                        label="First name"
                        required
                    ></v-text-field>
                    </v-col>

                    
                    <v-col
                    cols="12"
                    md="4"
                    >
                    <v-text-field
                    v-model="email"
                    name="email"
                    :rules="emailRules"
                    label="E-mail"
                  
                    required
                    ></v-text-field>
                    </v-col>
                    <v-col
                    cols="12"
                    md="4"
                    >
                    <v-textarea label="Message" :rules="msgRules" 
                        name="message" v-model="message"></v-textarea>
                    </v-col>
                </v-row>
                </v-container>
                <v-btn
                    :loading="loading"
                    type="submit"
                    block
                    class="mt-2"
                    text="Submit"
                ></v-btn>
            </v-form>
        </div>
    </main>
</template>

<script>
  export default {
    data: () => ({
      valid: false,
      loading: false,
      firstname: '',
      message: '',
      nameRules: [
        value => {
          if (value) return true

          return 'Name is required.'
        },
        value => {
          if (value?.length <= 10) return true

          return 'Name must be less than 10 characters.'
        },
      ],
      email: '',
      emailRules: [
        value => {
          if (value) return true

          return 'E-mail is requred.'
        },
        value => {
          if (/.+@.+\..+/.test(value)) return true

          return 'E-mail must be valid.'
        },
      ],
      msgRules: [
        value => {
          if (value) return true

          return 'Message is required'
        },
      ],
    }),
    methods: {
      onSubmit(event){
        event.preventDefault()
        if(this.valid) {
          event.srcElement.submit()
          this.firstname = ''
          this.message = ''
          this.email = ''
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
    main {
      scroll-margin-top: 10px;
    }
    .sub-content {
        font-size: 16px;
        padding: 0 1rem;
        margin: auto;
        color: #333;
        text-align: center;
        width: 100%;
        line-height: 2rem;
    }
    .v-form{
        margin-top: 3rem;
        text-align: center;
        button {
            margin: 0 auto;
            margin-bottom: 2rem;
            text-align: center;
            min-width: unset;
            width: 58% !important;
            font-family: 'Source Sans 3', sans-serif;
            height: 3.3rem !important;
            background-color: #C70039;
            color: #fff;
            font-size: 16px;
            @media only screen and (min-width: 600px) {
                width: 18% !important;
            }
        }
    }
    .content {
        position: relative;
        width: 82%;
        text-align: center;
        letter-spacing: 3px;
        color: #000;
        font-family: "Source Sans 3", sans-serif;
        padding: 3rem 0 2rem 0;
        margin: auto;
        font-size: 35px;
        font-weight: 800;
        &::after{
            content: "";
            position: absolute;
            bottom: 0;
            margin-left: auto;
            margin-right: auto;
            left: 0;
            right: 0;
            text-align: center;
            height: 0.7em;
            width: 7vw;
            border-radius: 10%;
            border-top: 5px solid #C70039;
        }
    }
</style>