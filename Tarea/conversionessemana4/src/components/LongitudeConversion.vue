<template>
    <div id="root">

        <div class="card" style="width: 24rem;">
            
            <div class="card-header text-white mb-3" style="background-color:#001485">Convertir Longitudes</div>
            <!-- tabla que contiene los campos -->
            <div class="card-body">
                <p class="card-text">
                <table>
                    <thead>
                        <th>Opciones</th>
                        <th>Valores</th>
                    </thead>
                    <tbody>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion1">
                                    <option value="Mi">Millas</option>
                                    <option value="Km">Kilómetros</option>
                                    <option value="M">Metros</option>
                                    <option value="Yd">Yardas</option>
                                    <option value='Ft'>Pies</option>
                                    <option value='In'>Pulgadas</option>
                                    <option value='Cm'>Centímetros</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="dato"></td>
                        </tr>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion2">
                                    <option value="Mi">Millas</option>
                                    <option value="Km">Kilómetros</option>
                                    <option value="M">Metros</option>
                                    <option value="Yd">Yardas</option>
                                    <option value='Ft'>Pies</option>
                                    <option value='In'>Pulgadas</option>
                                    <option value='Cm'>Centímetros</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="resultado" readonly></td>
                        </tr>
                    </tbody>
                </table>
                </p>
                <button class="btn text-white" style="background-color:#5400c2" v-on:click="convertirL()">Calcular</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'LongitudeConversion',
    data(){
        return{
            seleccion1:'M',
            seleccion2:'Cm',
            dato:0,
            resultado:0
        }
    },
    methods:{
        convertirL(){
            //Milla
            if (this.seleccion1 == 'Mi' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*1.60934;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'M') {
                this.resultado = this.dato*1609.34;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*1760;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*5280;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'In') {
                this.resultado = this.dato *63360;
            } else if (this.seleccion1 == 'Mi' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato *160934;
            }
            //Kilómetro
            if (this.seleccion1 == 'Km' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.621371;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'Km') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'M') {
                this.resultado = this.dato*1000;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*1093.61;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*3280.84;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'In') {
                this.resultado = this.dato *39370.1;
            } else if (this.seleccion1 == 'Km' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato * 100000;
            }
            //Metros
            if (this.seleccion1 == 'M' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.000621371;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*0.001;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'M') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*1.09361;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*3.28084;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'In') {
                this.resultado = this.dato*39.3701;
            } else if (this.seleccion1 == 'M' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato*100;
            }
            //Yarda
            if (this.seleccion1 == 'Yd' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.000568182;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*0.0009144;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'M') {
                this.resultado = this.dato*0.9144;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*3;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'In') {
                this.resultado = this.dato*36;
            } else if (this.seleccion1 == 'Yd' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato*91.44;
            }
            //Pies
           if (this.seleccion1 == 'Ft' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.000189394;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*0.0003048;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'M') {
                this.resultado = this.dato*0.3048;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*0.333333;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'In') {
                this.resultado = this.dato*12;
            } else if (this.seleccion1 == 'Ft' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato*30.48;
            }

            //Pulgadas
            if (this.seleccion1 == 'In' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.0000157828;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*0.0000254;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'M') {
                this.resultado = this.dato*0.254;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*0.0277778;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*0.0833333;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'In') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'In' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato*2.54;
            }

            //Centimetros
            if (this.seleccion1 == 'Cm' && this.seleccion2 == 'Mi') {
                this.resultado = this.dato*0.00000621371;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'Km') {
                this.resultado = this.dato*0.00001;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'M') {
                this.resultado = this.dato*0.01;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'Yd') {
                this.resultado = this.dato*0.0109364;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'Ft') {
                this.resultado = this.dato*0.0328084;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'In') {
                this.resultado = this.dato*0.393701;
            } else if (this.seleccion1 == 'Cm' && this.seleccion2 == 'Cm') {
                this.resultado = this.dato;
            }
        },
        
    }
}
</script>