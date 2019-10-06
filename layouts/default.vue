<template>
  <div>
    <nuxt />
  </div>
</template>

<style lang="scss">
// Global styling for this template
body,
html {
  width: 100vw;
  overflow-x: hidden;
}

body {
  background: url(https://previews.123rf.com/images/1stchoice/1stchoice1607/1stchoice160700017/59848409-light-gray-background-with-soft-texture.jpg)
    no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  position: relative;
}

// Typography
.text-white-75 {
  color: fade-out(white, 0.25);
}

// Custom horizontal rules
hr.divider {
  max-width: 3.25rem;
  border-width: 0.2rem;
  border-color: $primary;
}

hr.light {
  border-color: white;
}

.btn {
  clear: both;
  color: #fff;
  border: 2px solid;
  border-radius: 3px;
  text-align: center;
  text-decoration: none;
  display: block;
  font-family: sans-serif;
  font-size: 14px;
  width: 13em;
  padding: 5px 10px;
  font-weight: 600;
  position: absolute;
  bottom: 20px;
  left: 0;
  right: 0;
  margin: 0 auto;
  background: rgba(0, 0, 0, 0.2);
  box-shadow: 0 0 0px 3px rgba(0, 0, 0, 0.2);
  opacity: 0.4;
}
.btn:hover {
  color: #fff;
  opacity: 1;
}

.btn-xl {
  padding: 1.25rem 2.25rem;
  font-size: 0.85rem;
  font-weight: 700;
  text-transform: uppercase;
  border: none;
  border-radius: 10rem;
}

// Page section padding
.page-section {
  padding: 2rem 0;
}
</style>
