<script>
  export default {
    computed: {
      spinnerColor() {
        return this.color || this.$parent.color || '#ccc';
      },

      spinnerSize() {
        return '1rem';
      }
    },

    props: {
      size: Number,
      color: String
    }
  };
</script>
