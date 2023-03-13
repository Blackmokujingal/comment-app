// src/components/CommentForm.vue

<script>
export default {
  data() {
    return {
      comment: {
        email: '',
        name: '',
        firstname: '',
        birthdate: '',
        content: '',
      },
      errors: {},
    };
  },
  methods: {
    submitComment() {
      this.errors = {};
      this.$http.post('/api/comments', this.comment)
        .then(response => {
          console.log(response.data);
          alert('Commentaire soumis avec succès !');
        })
        .catch(error => {
          console.log(error.response.data);
          this.errors = error.response.data.violations.reduce((result, violation) => {
            result[violation.propertyPath] = violation.title;
            return result;
          }, {});
        });
    },
  },
};
</script>
