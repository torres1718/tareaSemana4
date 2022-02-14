<template>
    <div id="root">

        <div class="card" style="width: 24rem;">
            
            <div class="card-header text-white mb-3" style="background-color:#001485">{{titulo}}</div>
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
                                    <option value="dl">Dolar</option>
                                    <option value="eu">Euro</option>
                                    <option value="ye">Yen</option>
                                    <option value="cl">Colón</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="dato"></td>
                        </tr>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion2">
                                    <option value="dl">Dolar</option>
                                    <option value="eu">Euro</option>
                                    <option value="ye">Yen</option>
                                    <option value="cl">Colón</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="resultado" readonly></td>
                        </tr>
                    </tbody>
                </table>
                </p>
                <button class="btn text-white" style="background-color:#5400c2" v-on:click="convertirT()">Calcular</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'MonedaConversion',
    props:{titulo: String},
    data(){
        return{
            seleccion1:'dl',
            seleccion2:'eu',
            dato:0,
            resultado:0
        }
    },
    methods:{
        convertirT(){
            //dolar
            if (this.seleccion1 == 'dl' && this.seleccion2 == 'dl') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'dl' && this.seleccion2 == 'eu') {
                this.resultado = this.dato*0.88;
            } else if (this.seleccion1 == 'dl' && this.seleccion2 == 'ye') {
                this.resultado = this.dato*115.50;
            } else if (this.seleccion1 == 'dl' && this.seleccion2 == 'cl') {
                this.resultado = this.dato*8.79;

            }
            //euro
            if (this.seleccion1 == 'eu' && this.seleccion2 == 'dl') {
                this.resultado = this.dato*1.14;
            } else if (this.seleccion1 == 'eu' && this.seleccion2 == 'eu') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'eu' && this.seleccion2 == 'ye') {
                this.resultado = this.dato*131.21;
            } else if (this.seleccion1 == 'eu' && this.seleccion2 == 'cl') {
                this.resultado = this.dato*9.98;
            }
            //yen
            if (this.seleccion1 == 'ye' && this.seleccion2 == 'dl') {
                this.resultado = this.dato*0.0087;
            } else if (this.seleccion1 == 'ye' && this.seleccion2 == 'eu') {
                this.resultado = this.dato*0.0076;
            } else if (this.seleccion1 == 'ye' && this.seleccion2 == 'ye') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'ye' && this.seleccion2 == 'cl') {
                this.resultado = this.dato*0.076;

            }
            //colón
            if (this.seleccion1 == 'cl' && this.seleccion2 == 'dl') {
                this.resultado = this.dato*0.114;
            } else if (this.seleccion1 == 'cl' && this.seleccion2 == 'eu') {
                this.resultado = this.dato*0.10;
            } else if (this.seleccion1 == 'cl' && this.seleccion2 == 'ye') {
                this.resultado = this.dato*13.145;
            } else if (this.seleccion1 == 'cl' && this.seleccion2 == 'cl') {
                this.resultado = this.dato;
            }

        },
        
    }
}
</script>


