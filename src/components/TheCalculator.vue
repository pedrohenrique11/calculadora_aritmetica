<script>
export default {
  data() {
    return {
      expression: '',
      buttons: [
        ['7', '4', '1', '0', 'sin', 'asin', '%'],
        ['8', '5', '2', '.', 'cos', 'acos', '^'],
        ['9', '6', '3', '=', 'tan', 'atan', '('],
        ['/', '*', '-', '+', 'C', 'log', ')'],
      ],
    };
  },
  methods: {
    handleButtonClick(button) {
      switch(button) {
        case '=':
          this.calculateResult();
          break;
        case 'C':
          this.clearExpression(); // Troque para clearExpression
          break;
        case 'sqrt':
          this.calculateSquareRoot();
          break;
        case '%':
          this.calculatePercentage();
          break;
        case '^':
          this.addPowerSymbol();
          break;
        case 'sin':
          this.calculateSine();
          break;
        case 'cos':
          this.calculateCosine();
          break;
        case 'tan':
          this.calculateTangent();
          break;
        case 'asin':
          this.calculateArcSine();
          break;
        case 'acos':
          this.calculateArcCosine();
          break;
        case 'atan':
          this.calculateArcTangent();
          break;
        case 'log':
            this.calculateLog();
          break;
        case '(':
          this.expression += button;
          break;
        case ')':
          this.expression += button;
          break;
        default:
          this.expression += button;
      }
    },
    calculateResult() {
      try {
        this.expression = eval(this.expression).toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    clearExpression() {
      this.expression = '';
    },
    calculateSquareRoot() {
      try {
        this.expression = Math.sqrt(eval(this.expression)).toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    calculatePercentage() {
      try {
        this.expression = (eval(this.expression) / 100).toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    addPowerSymbol() {
      this.expression += '**';
    },
    calculateSine() {
      try {
        const result = Math.sin(eval(this.expression));
        this.expression = result.toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    calculateCosine() {
      try {
        const result = Math.cos(eval(this.expression));
        this.expression = result.toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    calculateTangent() {
      try {
        const result = Math.tan(eval(this.expression));
        this.expression = result.toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    calculateArcCosine() {
    try {
        const value = eval(this.expression);
        if (value >= -1 && value <= 1) {
        const result = Math.acos(value);
        this.expression = result.toString();
        } else {
        this.expression = 'Erro: Argumento fora do intervalo [-1, 1]';
        }
    } catch (error) {
        this.expression = 'Erro';
    }
    },
    calculateArcSine() {
    try {
        const value = eval(this.expression);
        if (value >= -1 && value <= 1) {
        const result = Math.asin(value);
        this.expression = result.toString();
        } else {
        this.expression = 'Erro: Argumento fora do intervalo [-1, 1]';
        }
    } catch (error) {
        this.expression = 'Erro';
    }
    },
    calculateArcTangent() {
        try {
        const result = Math.atan(eval(this.expression));
        this.expression = result.toString();
      } catch (error) {
        this.expression = 'Erro';
      }
    },
    calculateLog() {
        try{
            const result = Math.log(eval(this.expression));
            this.expression = result.toString();
        } catch (error) {
            this.expression = 'Error';
        }
    }
  },
};
</script>

<template>
  <div class="calculator">
    <input v-model="expression" type="text" disabled>
    <div class="buttons">
      <div v-for="row in buttons" :key="row">
        <button v-for="button in row" :key="button" @click="handleButtonClick(button)">
          {{ button }}
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 6rem auto;
  background-color: #f4f4f4;
  border-radius: 8px;
  padding: 20px;
}

input {
  width: 100%;
  padding: 10px;
  font-size: 18px;
  margin-bottom: 15px;
  box-sizing: border-box;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: none;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  width: 100%;
  padding: 1rem;
  margin: 0.4rem 0;
  font-size: 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  background-color: #41b883;
  color: white;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #3e8f61;
}
</style>
