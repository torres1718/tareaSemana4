<template>
    <div id="root">

        <div class="card" style="width: 24rem;">
            
            <div class="card-header text-white mb-3" style="background-color:#001485">Convertir masa</div>
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
                                    <option value="Kg">Kilogramos</option>
                                    <option value="Hg">Hectogramos</option>
                                    <option value="Dg">Decagramos</option>
                                    <option value="Gr">Gramos</option>
                                    <option value='Dig'>Decigramos</option>
                                    <option value='Cg'>Centigramos</option>
                                    <option value='Mg'>Miligramos</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="dato"></td>
                        </tr>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion2">
                                   <option value="Kg">Kilogramos</option>
                                    <option value="Hg">Hectogramos</option>
                                    <option value="Dg">Decagramos</option>
                                    <option value="Gr">Gramos</option>
                                    <option value='Dig'>Decigramos</option>
                                    <option value='Cg'>Centigramos</option>
                                    <option value='Mg'>Miligramos</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="resultado" readonly></td>
                        </tr>
                    </tbody>
                </table>
                </p>
                <button class="btn text-white" style="background-color:#5400c2" v-on:click="convertirM()">Calcular</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'MassConversion',
    data(){
        return{
            seleccion1:'Kg',
            seleccion2:'Gr',
            dato:0,
            resultado:0
        }
    },
    methods:{
        convertirM(){
            //Kilogramo
            if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato*10;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato*100;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato*1000;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato*10000;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato * 100000;
            } else if (this.seleccion1 == 'Kg' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 1000000;
            }
            //Hectogramo
            if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato*10;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato*100;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato*1000;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato * 10000;
            } else if (this.seleccion1 == 'Hg' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 100000;
            }
            //Decagramo
            if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/100;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato*10;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato*100;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato * 1000;
            } else if (this.seleccion1 == 'Dg' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 10000;
            }
            //Gramo 
            if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/1000;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato/100;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato*10;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato * 100;
            } else if (this.seleccion1 == 'Gr' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 1000;
            }
            //Decigramo
           if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/10000;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato/1000;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato/100;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato * 10;
            } else if (this.seleccion1 == 'Dig' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 100;
            }

            //Centigramo
            if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/100000;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato/10000;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato/1000;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato/100;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Cg' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato * 10;
            }

            //Miligramo
            if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Kg') {
                this.resultado = this.dato/1000000;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Hg') {
                this.resultado = this.dato/100000;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Dg') {
                this.resultado = this.dato/10000;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Gr') {
                this.resultado = this.dato/1000;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Dig') {
                this.resultado = this.dato/100;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Cg') {
                this.resultado = this.dato/10;
            } else if (this.seleccion1 == 'Mg' && this.seleccion2 == 'Mg') {
                this.resultado = this.dato;
            }
        },
        
    }
}
</script>