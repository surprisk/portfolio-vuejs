<script>

export default {
  components : {},
  methods:{
  },
  props: {
    attrs: {
      type: Object
    }
  }
}
</script>
<template>
  <div class="form-item">
    <input :="this.attrs" type="submit"/>
  </div>
</template>

<style scoped>
  .form-item{
    width: 100%;
    text-align: center;
  }

  input{
    padding: .6rem 1.5rem;
    border-radius: 3px;
    border: 2px solid rgb(28, 114, 216);
    color: rgb(28, 114, 216);
    outline: none;
    margin-top: .6rem;
    background-color: transparent;
  }

  input:is(:hover, :active, :focus) {
    background-color: rgb(28, 114, 216);
    color: rgb(246, 245, 240)
  }

</style>
