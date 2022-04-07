<template>
  <div>
    <h1>Home Sweet Home by Immo2000</h1>
    <Preview-Estate />
  </div>
</template>

<script>
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Antonio&family=Lato:wght@700&display=swap");

:root {
  /* Colors */
  --c-white: #fff;
  --c-black: #111111;
  --c-grey: #dbdbdb;
  --c-primary: #f2a0c4;
  --c-secondary: #81bfde;
  --c-warning: #f25572;
  /* Font family */
  --ff-lato: "Lato", sans-serif;
  /* Font size */
  --ratio: 1.2;
  --fs-sm: calc(var(--fs-m) / var(--ratio));
  --fs-m: 1em;
  --fs-l: calc(var(--fs-m) * var(--ratio));
  --fs-xl: calc(var(--fs-l) * var(--ratio));
  --fs-xxl: calc(var(--fs-xl) * var(--ratio));
  /* Font weight */
  --fw-regular: 400;
  --fw-bold: 700;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

* {
  margin: 0;
  padding: 0;
}

html {
  font-size: var(--fs-m);
  font-family: var(--ff-lato);
  line-height: 1.75;
  font-weight: var(--fw-regular);
}

body {
  padding: 2rem;
  background-color: var(--c-primary);
  -webkit-font-smoothing: antialiased;
}

main {
  margin-top: 2rem;
  padding: 2rem;
  background-color: var(--c-white);
  border-radius: 5px;
}

img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}

:is(a, a:hover, button) {
  color: inherit;
  text-decoration: none;
}

li {
  list-style: none;
}

h1,
h2,
h3,
h4,
h5,
h6,
p,
blockquote {
  max-width: 80ch;
}
</style>