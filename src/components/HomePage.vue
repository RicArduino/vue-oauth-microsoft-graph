<template>
  <div class="container">
    
    <div class="content">
      Here comes the content of the HomePage.
      
      <!-- Bouton Primary -->
      <button class="base-button base-button--primary" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus">
        BaseButton
      </button>

      <!-- Bouton Disabled -->
      <button class="base-button base-button--disabled" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus" disabled>
        BaseButton disabled
      </button>

      <!-- Bouton Danger -->
      <button class="base-button base-button--danger" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus">
        BaseButton with color props
      </button>

      <!-- Bouton Warn -->
      <button class="base-button base-button--warn" @mouseover="hover" @mouseleave="unhover" @focus="focus" @blur="unfocus">
        BaseButton with color props
      </button>

      <button 
  class="base-button base-button--primary" 
  @click="handleAsyncClick" 
  :disabled="isLoading"
>
  <span v-if="isLoading" class="loading-icon"></span>
  Disabled and animated for 2 seconds if clicked
</button>

    </div>
  </div>
</template>

<script>
export default {
  
  data() {
  return {
    isLoading: false,
    clickCount: 0  
  }
},

  methods: {
    hover(event) {
      event.target.style.backgroundColor = "#45a049";
    },
    unhover(event) {
      if (event.target.classList.contains("base-button--primary")) {
        event.target.style.backgroundColor = "#4CAF50";
      } else if (event.target.classList.contains("base-button--danger")) {
        event.target.style.backgroundColor = "#e53935";
      } else if (event.target.classList.contains("base-button--warn")) {
        event.target.style.backgroundColor = "#ff5722";
      }
    },
    focus(event) {
      event.target.style.backgroundColor = "#45a049";
    },
    unfocus(event) {
      this.unhover(event);
    },

  handleAsyncClick() {
    this.isLoading = true;
    this.clickCount++;  // Augmentez le compteur de clics à chaque clic

    new Promise((resolve) => {
      setTimeout(() => {
        this.isLoading = false;
        resolve();
      }, 1000 * this.clickCount);  // Multipliez le temps d'attente par le nombre de clics
    });
  }
  },
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

.base-button--primary {
  background-color: #42b983;
}

.base-button--primary:hover, .base-button--primary:focus {
  background-color: #45a049;
}

.base-button--warn {
  background-color: #ff5722;
}

.base-button--warn:hover, .base-button--warn:focus {
  background-color: #ff7043;
}

.base-button--danger {
  background-color: #e53935;
}

.base-button--danger:hover, .base-button--danger:focus {
  background-color: #ef5350;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.loading-icon {
  border: 4px solid rgba(255,255,255,0.3);
  border-radius: 50%;
  border-top: 4px solid white;
  width: 24px;
  height: 24px;
  animation: spin 1s linear infinite;
  margin-right: 5px;
}
</style>