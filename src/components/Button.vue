<template>
  <div class="Button-box">
    <button class="Button">按钮</button>
  </div>
</template>

<script>
export default {
  props: ['sourceCodeLink', 'title'],
  methods: {
    openMyGithub() {
      const a = document.createElement('a')
      a.target = '_blank'
      a.href = 'https://github.com/Dark-YiFeng'
      a.click()
    },
    toMainPage() {
      this.$emit('to-main-page')
    }
  }
}
</script>

<style scoped>
.Button{
color: #fff;
  position: relative;
  background: orangered;
  border: none;
  color: white;
  padding: 15px 24px;
  font-size: 1.4rem;
  outline: none;
  box-shadow: -6px 6px 0 hsl(16, 100%, 30%);
}
.Button::before {
  content: "";
  display: block;
  width: 0;
  height: 0;
  position: absolute;
  top: 0;
  left: -6px;
  border: 6px solid transparent;
  border-right: 6px solid hsl(16, 100%, 30%);
  border-left-width: 0px;
}

.Button::after {
  content: "";
  display: block;
  width: 0;
  height: 0;
  position: absolute;
  bottom: -6px;
  right: 0;
  border: 6px solid transparent;
  border-top: 6px solid hsl(16, 100%, 30%);
  border-bottom-width: 0px;
}

.Button:active {
  background: hsl(16, 100%, 40%);
  top: 3px;
  left: -3px;
  box-shadow: -3px 3px 0 hsl(16, 100%, 30%);
}

.Button:active::before {
  border: 3px solid transparent;
  border-right: 3px solid hsl(16, 100%, 30%);
  border-left-width: 0px;
  left: -3px;
}

.Button::after {
  border: 3px solid transparent;
  border-top: 3px solid hsl(16, 100%, 30%);
  border-bottom-width: 0px;
  bottom: -3px;
}
</style>
