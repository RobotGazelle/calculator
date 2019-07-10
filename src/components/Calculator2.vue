<template>
    <div id=Calculator>
        <h1>Gabo's Shiny Calculator</h1>
        <v-container>
            <v-layout>
                <v-flex xs4></v-flex>
                <v-flex xs4>
                    <v-card>
                        <v-layout column>
                            <v-layout row>
                                <v-flex xs6 pa-1>
                                    <v-btn block dark color="#00897B" @click="Clear()">Clear</v-btn>
                                </v-flex>
                                <v-flex xs3 pa-1>
                                    <v-btn block dark color="#00897B" @click="Bcksp()">
                                        <v-icon>backspace</v-icon>
                                    </v-btn>
                                </v-flex>
                            </v-layout>
                            <v-layout row>
                                
                            </v-layout>
                        </v-layout>

                            <v-layout wrap row>
                            <v-flex xs12 pa-2>
                            <!-- output -->
                                <v-card-text>
                                    <div>{{no1}} {{oper}} {{no2}}</div>
                                    <div>{{result}}</div>
                                </v-card-text>
                            </v-flex>
                            <v-flex xs6 pa-1>
                                 <v-btn block dark color="#00897B" @click="Clear()">Clear</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="Bcksp()">
                                    <v-icon>backspace</v-icon>
                                </v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setOper('*')">*</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(7)">7</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(8)">8</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(9)">9</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setOper('/')">/</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(4)">4</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(5)">5</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(6)">6</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setOper('+')">+</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(1)">1</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(2)">2</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(3)">3</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setOper('-')">-</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark depressed color="#00897B">
                                    <v-icon>sentiment_satisfied_alt</v-icon>
                                </v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="setNumbers(0)">0</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark depressed color="#00897B">
                                    <v-icon>mood</v-icon>
                                </v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickEquals('=')">=</v-btn>
                            </v-flex>
                        </v-layout>
                    </v-card>
                </v-flex>
                <v-flex xs4></v-flex>
            </v-layout>
            
            
        </v-container>
    </div>
    
</template>


<script>
export default {
    data: function () {
        return {
            result: null,
            no1: null,
            no2: null,
            oper: null,
        }  
    },
    methods: {
        setNumbers (number) {
            if (this.oper === null) {
                if (this.no1 === null) {
                    this.no1 = number
                } else {
                    this.no1 = this.no1 * 10 + number
                }
            } else {
                if (this.no2 === null) {
                    this.no2 = number
                } else {
                    this.no2 = this.no2 * 10 + number
                }
            }
        },
        setOper(oper) {
            if (this.oper === null) {
                this.oper = oper
            }
        },
        onClickEquals() {
            if (this.oper === "+") {
                this.result = this.no1 + this.no2
            } else if (this.oper === "-") {
                this.result = this.no1 - this.no2
            } else if (this.oper === "*") {
                this.result = this.no1 * this.no2
            } else if (this.oper === "/") {
                this.result = this.no1 / this.no2
            }
             
        },
        Clear() {
            this.result = null;
            this.no1 = null;
            this.no2 = null;
            this.oper = null;
        },
        Bcksp() {
            if (this.no2 !== null) {
                if (this.no2 > 9) {
                    this.no2 = (this.no2 - this.no2 % 10) / 10
                } else this.no2 = null
            } else if (this.oper !== null) {
                this.oper = null
            } else if (this.no1 !== null) {
                if (this.no1 > 9) {
                    this.no1 = (this.no1 - this.no1 % 10) / 10
                } else this.no1 = null
            }
        }
    }
}
    
</script>