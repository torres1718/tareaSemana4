<template>
    <div id="root">

        <div class="card" style="width: 24rem;">
            
            <div class="card-header text-white mb-3" style="background-color:#001485">Convertir Almacenamiento</div>
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
                                    <option value="TB">TeraByte</option>
                                    <option value="GB">GigaByte</option>
                                    <option value="MB">MegaByte</option>
                                    <option value="KB">KiloByte</option>
                                    <option value='B'>Byte</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="dato"></td>
                        </tr>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion2">
                                    <option value="TB">TeraByte</option>
                                    <option value="GB">GigaByte</option>
                                    <option value="MB">MegaByte</option>
                                    <option value="KB">KiloByte</option>
                                    <option value='B'>Byte</option>
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
    name:'AlmacenamientoConversion',
    data(){
        return{
            seleccion1:'TB',
            seleccion2:'GB',
            dato:0,
            resultado:0
        }
    },
    methods:{
        convertirL(){
            //TeraByte
            if (this.seleccion1 == 'TB' && this.seleccion2 == 'TB') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'TB' && this.seleccion2 == 'GB') {
                this.resultado = this.dato*1024;
            } else if (this.seleccion1 == 'TB' && this.seleccion2 == 'MB') {
                this.resultado = this.dato*1048576;
            } else if (this.seleccion1 == 'TB' && this.seleccion2 == 'KB') {
                this.resultado = this.dato*1073741824;
            } else if (this.seleccion1 == 'TB' && this.seleccion2 == 'B') {
                this.resultado = this.dato*1099511627776;
            } 
            //GigaByte
            if (this.seleccion1 == 'GB' && this.seleccion2 == 'TB') {
                this.resultado = this.dato*0.00097656;
            } else if (this.seleccion1 == 'GB' && this.seleccion2 == 'GB') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'GB' && this.seleccion2 == 'MB') {
                this.resultado = this.dato*1024;
            } else if (this.seleccion1 == 'GB' && this.seleccion2 == 'KB') {
                this.resultado = this.dato*1048576;
            } else if (this.seleccion1 == 'GB' && this.seleccion2 == 'B') {
                this.resultado = this.dato*1073741824;
            } 
            //MegaByte
            if (this.seleccion1 == 'MB' && this.seleccion2 == 'TB') {
                this.resultado = this.dato*(9.5367431640625*(Math.pow(10,-7)));
            } else if (this.seleccion1 == 'MB' && this.seleccion2 == 'GB') {
                this.resultado = this.dato*0.00097656;
            } else if (this.seleccion1 == 'MB' && this.seleccion2 == 'MB') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'MB' && this.seleccion2 == 'KB') {
                this.resultado = this.dato*1024;
            } else if (this.seleccion1 == 'MB' && this.seleccion2 == 'B') {
                this.resultado = this.dato*1048576;
            } 
            //KiloByte
            if (this.seleccion1 == 'KB' && this.seleccion2 == 'TB') {
                this.resultado = this.dato*(9.313225746154785*(Math.pow(10, -10)));
            } else if (this.seleccion1 == 'KB' && this.seleccion2 == 'GB') {
                this.resultado = this.dato*(9.5367431640625*(Math.pow(10, -7)));
            } else if (this.seleccion1 == 'KB' && this.seleccion2 == 'MB') {
                this.resultado = this.dato*0.00097656;
            } else if (this.seleccion1 == 'KB' && this.seleccion2 == 'KB') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'KB' && this.seleccion2 == 'B') {
                this.resultado = this.dato*1024;
            } 
            //Byte
           if (this.seleccion1 == 'B' && this.seleccion2 == 'TB') {
                this.resultado = this.dato*(9.094947017729282*(Math.pow(10, -13)));
            } else if (this.seleccion1 == 'B' && this.seleccion2 == 'GB') {
                this.resultado = this.dato*(9.313225746154785*(Math.pow(10, -10)));
            } else if (this.seleccion1 == 'B' && this.seleccion2 == 'MB') {
                this.resultado = this.dato*(9.5367431640625*(Math.pow(10, -7)));
            } else if (this.seleccion1 == 'B' && this.seleccion2 == 'KB') {
                this.resultado = this.dato*0.00097656;
            } else if (this.seleccion1 == 'B' && this.seleccion2 == 'B') {
                this.resultado = this.dato;
            } 
        },
        
    }
}
</script>