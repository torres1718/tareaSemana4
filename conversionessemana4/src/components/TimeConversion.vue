<template>
    <div id="root">

        <div class="card" style="width: 24rem;">
            
            <div class="card-header text-white mb-3" style="background-color:#001485">Convertir tiempo</div>
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
                                    <option value="As">Años</option>
                                    <option value="Ms">Meses</option>
                                    <option value="Sms">Semanas</option>
                                    <option value="Ds">Días</option>
                                    <option value='Hrs'>Horas</option>
                                    <option value='Mins'>Minutos</option>
                                    <option value='Secs'>Segundos</option>
                                </select>
                            </td>
                            <td><input type="number" v-model="dato"></td>
                        </tr>
                        <tr>
                            <td>
                                <select class="form-select" aria-label="Default select example" v-model="seleccion2">
                                    <option value="As">Años</option>
                                    <option value="Ms">Meses</option>
                                    <option value="Sms">Semanas</option>
                                    <option value="Ds">Días</option>
                                    <option value='Hrs'>Horas</option>
                                    <option value='Mins'>Minutos</option>
                                    <option value='Secs'>Segundos</option>
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
    name:'TimeConversion',
    data(){
        return{
            seleccion1:'Mins',
            seleccion2:'Secs',
            dato:0,
            resultado:0
        }
    },
    methods:{
        convertirT(){
            //años
            if (this.seleccion1 == 'As' && this.seleccion2 == 'As') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato*12;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato*52.143;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato*365;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato*8760;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato * 525600;
            } else if (this.seleccion1 == 'As' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 31540000;
            }
            //meses
            if (this.seleccion1 == 'Ms' && this.seleccion2 == 'As') {
                this.resultado = this.dato/12;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato*4.345;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato*30.417;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato*730;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato * 43800;
            } else if (this.seleccion1 == 'Ms' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 2628000;
            }
            //semanas
            if (this.seleccion1 == 'Sms' && this.seleccion2 == 'As') {
                this.resultado = this.dato/52.143;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato/4.345;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato*7;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato*168;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato * 10080;
            } else if (this.seleccion1 == 'Sms' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 604800;
            }
            //días
            if (this.seleccion1 == 'Ds' && this.seleccion2 == 'As') {
                this.resultado = this.dato/365;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato/30.417;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato/7;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato*24;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato * 1440;
            } else if (this.seleccion1 == 'Ds' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 86400;
            }
            //horas
           if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'As') {
                this.resultado = this.dato/8760;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato/730;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato/168;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato/24;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato * 60;
            } else if (this.seleccion1 == 'Hrs' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 3600;
            }

            //minutos
            if (this.seleccion1 == 'Mins' && this.seleccion2 == 'As') {
                this.resultado = this.dato/525600;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato/43800;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato/10080;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato/1440;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato/60;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato;
            } else if (this.seleccion1 == 'Mins' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato * 60;
            }

            //segundos
            if (this.seleccion1 == 'Secs' && this.seleccion2 == 'As') {
                this.resultado = this.dato/31540000;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Ms') {
                this.resultado = this.dato/2628000;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Sms') {
                this.resultado = this.dato/604800;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Ds') {
                this.resultado = this.dato/86400;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Hrs') {
                this.resultado = this.dato/3600;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Mins') {
                this.resultado = this.dato/60;
            } else if (this.seleccion1 == 'Secs' && this.seleccion2 == 'Secs') {
                this.resultado = this.dato;
            }
        }
    }
}
</script>