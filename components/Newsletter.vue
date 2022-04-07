<template>
  <div>
    <form @submit.prevent="formSubmit()">
      <Input
        v-model="email"
        id="email"
        type="email"
        name="email"
        :required="true"
        label="Email"
      />
      <Input
        v-model="cgu"
        id="cgu"
        type="checkbox"
        :required="true"
        label="CGU"
      />
      <button type="submit">S'inscrire à la newsletter</button>
    </form>
  </div>
  <!--  -->
</template>

<script>
export default {
  data() {
    return {
      email: "",
      cgu: false, 
    };  
  },
  methods: {
    formSubmit() {
      fetch("https://formspree.io/f/xeqnkbez", {
        method: "POST",
        body: JSON.stringify({
          email: this.email,
          cgu: this.cgu,
        }),
        headers: {
          Accept: "application/json",
          "Content-type": "applcation/json",
        },
      })
        .then((response) => {
          if (response.ok) {
            console.log("submit");
          } else {
            response.json().then((data) => {
              if (Object.hasOwn(data, "errors")) {
                console.log(
                  data["errors"].map((error) => error["message"]).join(", ")
                );
              } else {
                console.log("Oops! There was a problem submitting your form");
              }
            });
          }
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>