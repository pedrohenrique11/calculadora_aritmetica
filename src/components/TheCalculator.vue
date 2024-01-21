<script>
    export default {
        data() {
            return {
                expression: '',
                buttons: [
                ['7', '4', '1', '0', 'sin','asin', '%'],
                ['8', '5', '2', '.', 'cos','acos', '^'],
                ['9', '6', '3', '=', 'tan','atan', '('],
                ['/', '*', '-', '+', 'C','log', ')'],
                ],
                methods: {
                    handleButtonClick(button) {
                        switch(button) {
                            case '=':
                                this.calculateResult();
                                break;
                            case 'C':
                                this.clearResult();
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
                            calculateArcSine() {
                            try {
                                const result = Math.asin(eval(this.expression));
                                this.expression = result.toString();
                            } catch (error) {
                                this.expression = 'Erro';
                            }
                            },
                            calculateArcCosine() {
                            try {
                                const result = Math.acos(eval(this.expression));
                                this.expression = result.toString();
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
                            }
                        },
                                
                        }
                    }
                }
            
</script>

<template>
   <div class="calculator">
      <input v-model="expression" type="text" disabled>
      <div class="buttons">
        <div v-for="row in buttons" :key="row" v-if="row !== ''">
          <button v-for="button in row" :key="button" @click="handleButtonClick(button)">
            {{ button }}
          </button>
        </div>
      </div>
    </div>
</template>