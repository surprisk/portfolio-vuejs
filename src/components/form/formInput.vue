<script>
import IconLucide from '../icons/IconLucide.vue'

export default {
  data() {
    return {
      statePasswordVisibility: false,
      validationExpressions: {
        phone: /^(\+33|0033|0)(6|7)[0-9]{8}$/g,
        mail: /^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/g, // eslint-disable-line
        password: /^(?=.*[A-Za-z])(?=.*\d)(?=.*[@$!%*#?&])[A-Za-z\d@$!%*#?&]{8,}$/g //Minimum eight characters, at least one letter, one number and one special character
      }
    }
  },
  components: { IconLucide },
  methods: {
    visibilityInputPassword(event) {
      let handler = event.target
      let secureIndex = 0

      do {
        handler = handler.parentElement
        secureIndex++
      } while (!handler.classList.contains('form-item') && secureIndex < 5)

      handler.childNodes[1].type = this.statePasswordVisibility ? 'password' : 'text'
      this.statePasswordVisibility = !this.statePasswordVisibility
    },
    formValidation(event) {
      const { value, classList } = event.target
      const regex = this.validationExpressions[this.validation]

      !regex || value.match(regex) ? classList.remove('wrong') : classList.add('wrong')
    }
  },
  props: {
    labelContent: {
      type: String
    },
    attrs: {
      type: Object
    },
    validation: {
      type: String
    }
  }
}
</script>
<template>
  <div class="form-item">
    <label v-if="this.labelContent" :for="this.attrs?.id">{{ this.labelContent }}</label>
    <input :="this.attrs" @input="(event) => !this.validation || this.formValidation(event)" />
    <IconLucide
      v-if="this.attrs?.type == 'password'"
      iconSize="1.5rem"
      :icon="this.statePasswordVisibility ? 'EyeOff' : 'Eye'"
      class="input-password-icon"
      @click="visibilityInputPassword"
    ></IconLucide>
  </div>
</template>

<style scoped>
.form-item {
  width: 100%;
  position: relative;
}

input {
  padding: 0.6rem 0.4rem;
  border-radius: 3px;
  border: 1px solid rgb(226, 226, 225);
  outline: none;
  width: 100%;
  margin-top: 0.6rem;
}

input:focus {
  outline: 2px solid rgb(28, 114, 216);
}

.wrong {
  outline: 2px solid rgb(255, 97, 88);
}

.input-password-icon {
  position: absolute;
  line-height: 0;
  right: 0.4rem;
  bottom: 0.5rem;
  cursor: pointer;
}
</style>
