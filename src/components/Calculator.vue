<template>
    <div id=Calculator>
        <h1>Gabo's Shiny Calculator</h1>
        <v-container>
            <v-layout>
                <v-flex xs4></v-flex>
                <v-flex xs4>
                    <v-card>
                        <v-layout wrap row>
                            <v-flex xs12 pa-2>
                            <!-- output -->
                                <v-card-text>
                                    <div>{{no1}} {{oper}} {{no2}}</div>
                                    <div>{{result}}</div>
                                </v-card-text>
                            </v-flex>
                            <v-flex xs6 pa-1>
                                 <v-btn block dark color="#00897B" @click="onClickClear()">Clear</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B">
                                    <v-icon>backspace</v-icon>
                                </v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickOper('*')">*</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(7)">7</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(8)">8</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(9)">9</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickOper('/')">/</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(4)">4</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(5)">5</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(6)">6</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickOper('+')">+</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(1)">1</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(2)">2</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(3)">3</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickOper('-')">-</v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark depressed color="#00897B">
                                    <v-icon>sentiment_satisfied_alt</v-icon>
                                </v-btn>
                            </v-flex>
                            <v-flex xs3 pa-1>
                                <v-btn block dark color="#00897B" @click="onClickNo(0)">0</v-btn>
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
        onClickNo(number) {
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
        onClickOper(oper) {
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
        onClickClear() {
            this.result = null;
            this.no1 = null;
            this.no2 = null;
            this.oper = null;
        }
    },
    computed: {
        
    }
}
    
</script>

<style>


</style>

