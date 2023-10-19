<template>
    <div class="container">
      
      <div class="content">
        Here comes the content of the HomePage.
        <button class="base-button" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus" :disabled="false">
        BaseButton with custom margin
      </button>
      <button class="base-button base-button--disabled" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus" :disabled="true">
        BaseButton disabled
      </button>
      </div>
    </div>
  </template>
  
  <script>
export default {
  methods: {
    hover() {
      this.$el.querySelector('.base-button').style.backgroundColor = "#45a049";
    },
    unhover() {
      this.$el.querySelector('.base-button').style.backgroundColor = "#4CAF50";
    },
    focus() {
      this.$el.querySelector('.base-button').style.backgroundColor = "#45a049";
    },
    unfocus() {
      this.$el.querySelector('.base-button').style.backgroundColor = "#4CAF50";
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;          
  flex-direction: column; 
  min-height: 100vh;     
  font-family: Arial, sans-serif;
}

.content {
  flex: 1;              
  padding: 20px;
  font-size: 18px;
}

.base-button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 12px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  cursor: pointer;
  border-radius: 4px;
  margin-right: 10px;
  transition: background-color 0.3s ease;
}

.base-button--disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>