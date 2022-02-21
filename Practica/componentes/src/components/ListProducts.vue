<template>
    <div id="root">
        <div class="container">
            <header class="d-flex flex-wrap justify-content-center py-3 mb-4 border-bottom">
                <span class="fs-4"><h1>{{title}}</h1></span>
                <ul class="nav nav-pills">
                    <li>
                        <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
                            <i class="fa fa-shopping-cart"></i>
                            <span class="badge bg-primary">{{itemCount}}</span>
                        </button>
                    </li>
                </ul>
            </header>
            <!--seccion de productos-->
            <div class="row row-cols-1 row-cols-md-3 mb-3 text-center">
                <div class="col-sm-6" v-for="(item, index) in items" v-bind:key="index">
                    <div class="card mb-4 rounded-3 shadow-sm">
                        <div class="card-header py-3">
                            <h4 class="my-0 fw-normal">{{item.productName}}</h4>
                        </div>
                        <div class="card-body">
                            <p class="card-text">
                                {{item.description}}
                                <div class="from-group row">
                                    <div class="col-xs-2">
                                        <h1>${{item.price}}</h1>
                                    </div>
                                    <ul class="list-unstyled mt-3 mb-4">
                                        <li><input type="number" v-model.number="item.quantity"/></li>
                                    </ul>
                                       
                                    
                                    <a class="btn btn-primary"
                                        v-on:click="addItem(index, item.productName, item.quantity)"
                                    >Add Cart</a>
                                </div>
                            
                        </div>   
                    </div>   
                </div>
            </div> 
        </div>
        <p v-if="itemsExist()"></p>
        <div class="footer">
            <label v-html="message"></label>
        </div>
    <!--incluimos el componente cartItems-->
    <cart-items :cartItems="cartItems" :itemCount="itemCount"/>

    </div>
</template>

<script>
//importar products.json
import products from '../assets/products.json'
import CartItems from './CartItems.vue'
export default{
    name:'ListProducts',
    props:{
        title:String
    },
    components:{
       CartItems
        
    },
    data(){
        return{
            items: products,
            cartItems:[],
            itemCount:0
        }
    },
    methods:{
        itemsExist: function(){
            if(this.cartItems.length>0){
                this.message='';
            }else{
                this.message="<h5 class='alert alert-danger'>Cart is empty</h5>"
            }
        },
        add:function(index){
            this.cartItems.push(
                {
                    productName: this.items[index].productName,
                    description: this.items[index].description,
                    price: this.items[index].price,
                    quantity: this.items[index].quantity
                }
            )
        },
        addItem: function(index, productName, quantity){
            if(this.cartItems.length>0){
                var exist=0;
                var i=0;               
                
                for(i=0; i<this.cartItems.length; i++){
                    if(this.cartItems[i].productName===productName){
                        exist=1
                        this.cartItems[i].quantity+=quantity;
                    }
                }
                if(exist==1){
                        alert("El producto ya existe en el carro");
                }
                else{
                    this.add(index);
                }
            }
            else{
                this.add(index);
            }
        }
    },
    watch:{
        cartItems:function(){
            this.itemCount=this.cartItems.length;
        }
    }
}
</script>