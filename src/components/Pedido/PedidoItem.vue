
<template>
  <v-card flat>
          

                 <v-card-text>                        
                    <v-row   >

                      <!--class="px-0"  paging cero  esto se aplica  tambien el componente padre -->
                        <v-col   class="px-0"    cols="12"  xs="12" sm="12"  md="12" lg="12" xl="12" >
                                      
                                            <template>

                                              <v-card-title>
                                              Bodega doña pepa
                                              </v-card-title>

                                              <v-data-table
                                                :headers="headers"
                                                :items="desserts"
                                                :search="search"
                                                dense
                                                sort-by="calories"
                                                class="elevation-1"
                                              >
                                                <template v-slot:top>
                                                  <v-toolbar flat color="white">
                                                    <!--
                                                    <v-toolbar-title>Bodega doña pepa</v-toolbar-title>
                                                    <v-divider
                                                      class="mx-4"
                                                      inset
                                                      vertical
                                                    ></v-divider>
                                                      <v-spacer></v-spacer>
                                                      -->
                                                  

                                                        <v-text-field
                                                      v-model="search"
                                                      append-icon="mdi-search"
                                                      label="Buscar"
                                                      solo
                                                      dense
                                                      single-line
                                                      hide-details
                                                    ></v-text-field>

                                                     <v-divider
                                                      class="mx-4"
                                                      inset
                                                      vertical
                                                    ></v-divider>

                                                            <v-menu
                                                                  transition="slide-x-transition"
                                                                  bottom
                                                                  right
                                                                >
                                                                  <template v-slot:activator="{ on }">
                                                                    <v-btn
                                                                      class="deep-white"
                                                                      color="primary"
                                                                      dark
                                                                      v-on="on"
                                                                      icon
                                                                    >
                                                                    <v-icon>mdi-dots-vertical</v-icon>
                                                                    
                                                                    </v-btn>
                                                                  </template>

                                                                  <v-list>
                                                                    <v-list-item  >
                                                                      <v-list-item-title>Eliminar</v-list-item-title>
                                                                    </v-list-item>
                                                                    <v-list-item  >
                                                                      <v-list-item-title>Mi bodega favorita</v-list-item-title>
                                                                    </v-list-item>
                                                                  </v-list>
                                                                </v-menu>



                                                      <!--
                                                    <v-dialog v-model="dialog" max-width="500px">
                                                      <template v-slot:activator="{ on }">
                                                        <v-btn color="primary" dark class="mb-2" v-on="on">New Item</v-btn>
                                                      </template>
                                                      <v-card>
                                                        <v-card-title>
                                                          <span class="headline">{{ formTitle }}</span>
                                                        </v-card-title>

                                                        <v-card-text>
                                                          <v-container>
                                                            <v-row>
                                                              <v-col cols="12" sm="6" md="4">
                                                                <v-text-field v-model="editedItem.name" label="Dessert name"></v-text-field>
                                                              </v-col>
                                                              <v-col cols="12" sm="6" md="4">
                                                                <v-text-field v-model="editedItem.calories" label="Calories"></v-text-field>
                                                              </v-col>
                                                              <v-col cols="12" sm="6" md="4">
                                                                <v-text-field v-model="editedItem.fat" label="Fat (g)"></v-text-field>
                                                              </v-col>
                                                              <v-col cols="12" sm="6" md="4">
                                                                <v-text-field v-model="editedItem.carbs" label="Carbs (g)"></v-text-field>
                                                              </v-col>
                                                              <v-col cols="12" sm="6" md="4">
                                                                <v-text-field v-model="editedItem.protein" label="Protein (g)"></v-text-field>
                                                              </v-col>
                                                            </v-row>
                                                          </v-container>
                                                        </v-card-text>

                                                        <v-card-actions>
                                                          <v-spacer></v-spacer>
                                                          <v-btn color="blue darken-1" text @click="close">Cancel</v-btn>
                                                          <v-btn color="blue darken-1" text @click="save">Save</v-btn>
                                                        </v-card-actions>
                                                      </v-card>
                                                    </v-dialog>
                                                -->

                                                  </v-toolbar>
                                                </template>
                                                <template v-slot:item.actions="{ item }">

                                                   
                                                     <v-btn  class="mx-2" color="primary" fab x-small dark>
                                                       <v-icon>mdi-plus-circle-outline</v-icon>
                                                      </v-btn>
                                                    
                                                    <v-btn  class="mx-2" color="primary" fab x-small dark>
                                                      <v-icon>mdi-minus-circle-outline</v-icon>
                                                    </v-btn>  
                                                  
                                                      <!--
                                                  <v-icon
                                                    small
                                                    class="mr-2"
                                                    @click="editItem(item)"
                                                    color="primary"
                                                  >
                                                   mdi-plus-circle-outline
                                                  </v-icon>
                                                  <v-icon
                                                    small
                                                    @click="deleteItem(item)"
                                                  >
                                                    mdi-plus-circle-outline
                                                  </v-icon>
                                                  -->
                                                </template>
                                                <template v-slot:no-data>
                                                  <v-btn color="primary" @click="initialize">Reset</v-btn>
                                                </template>
                                              </v-data-table>
                                            </template>

                          <v-divider
                            class="mx-6"
                            horizontal
                          ></v-divider>

                          <v-row>
                                <v-col class="px-6" xs6><strong class="primary--text" >TOTAL</strong> </v-col>
                                <v-col class="px-6" xs6> <strong class="primary--text">S/. 22.205</strong></v-col>
                          </v-row>

                                  
                        </v-col>
              

                    </v-row>

                   

              </v-card-text>

              <v-card-actions>
                  <v-spacer></v-spacer>
                    <v-row>

                      <div  class="my-2 mx-2">
                        <v-btn  large  color="warning" dark> Recoger <div class="hidden-sm-and-down small">tienda</div> </v-btn>                        
                      </div>
                    
                      <div class="my-2 mx-2">
                          <v-btn large  color="warning" dark> <div class="hidden-sm-and-down  small">Solicitar</div> delivery</v-btn>
                      </div>
                  </v-row>
              </v-card-actions>

              

        </v-card>
</template>






<script>
  export default {

//pasar propiedades  enjson dinamicos
      props:{
        //el componente  padre pasará los datos en un objeto
        dataObj:[
    //objeto datataable  (id del  producto de la bodega  por el cual sumar o restar)      
    //nombre bodega
    //id - codigo para eliminar bodega 


        ]



      },
    data: () => ({
      dialog: false,
      search: '',
      headers: [
        { text: 'Producto', value: 'producto' },
        { text: 'Cantidad', value: 'cantidad' },
        { text: 'Precio', value: 'precio' },
        { text: 'Opción', value: 'actions', sortable: false },
      ],
      desserts: [],
      editedIndex: -1,
      editedItem: {
        name: '',
        calories: 0,
        fat: 0,
        carbs: 0,
        protein: 0,
      },
      defaultItem: {
        name: '',
        calories: 0,
        fat: 0,
        carbs: 0,
        protein: 0,
      },
    }),

    computed: {
      formTitle () {
        return this.editedIndex === -1 ? 'New Item' : 'Edit Item'
      },
    },

    watch: {
      dialog (val) {
        val || this.close()
      },
    },

    created () {
      this.initialize()
    },

    methods: {
      initialize () {
        this.desserts = [
          {
            producto: 'ACEITE GIRASOL COCINERO PET X 1.5 LT',
            cantidad: 159,
            precio: 6.0,
            id: 24
          },
          {
            producto: 'ACEITE GIRASOL LEGITIMO PET X 900 CC',
            cantidad: 237,
            precio: 9.0,
            carbs: 37
          },
          {
            producto: 'ACEITUNAS VERDES DESCAROZADAS CASTELL DP X 80 GRS',
            cantidad: 262,
            precio: 16.0,
            id: 23
          },
          {
            producto: 'ACEITUNAS VERDES DSCRZDS DOY PCK YOVINESSA X150GRS',
            cantidad: 305,
            precio: 3.7,
            id: 67
          },
          {
            producto: 'AGUA SABORIZADA NARANJA SIN GAS AQUARIUS X 500 CC',
            cantidad: 356,
            precio: 16.0,
            carbs: 49
          },
          {
            producto: 'ANANA EN RODAJAS LIGHT CANALE X 825 GRS',
            cantidad: 375,
            precio: 0.0,
            id: 94
          },
          {
            producto: 'ARROLLADO RELLENO DULCE DE LECHE BLANCO ROLL X 6 U',
            cantidad: 392,
            precio: 0.2,
            id: 98
          },
          {
            producto: 'CEPILLO DENTAL DOBLE ACCION ALCANCE 60M PROX1UNI',
            cantidad: 408,
            precio: 3.2,
            id: 87
          },
          {
            producto: 'DESODORANTE AEROSOL ROMANTIC SPARK IMPULSE X 53GRS',
            cantidad: 452,
            precio: 25.0,
            id: 51
          },
          {
            producto: 'DULCE DE LECHE EST COLONIAL CAL LA SERENISIMAX250G',
            cantidad: 518,
            precio: 26.0,
            id: 65
          },
        ]
      },

      editItem (item) {
        this.editedIndex = this.desserts.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialog = true
      },

      deleteItem (item) {
        const index = this.desserts.indexOf(item)
        confirm('Are you sure you want to delete this item?') && this.desserts.splice(index, 1)
      },

      close () {
        this.dialog = false
        this.$nextTick(() => {
          this.editedItem = Object.assign({}, this.defaultItem)
          this.editedIndex = -1
        })
      },

      save () {
        if (this.editedIndex > -1) {
          Object.assign(this.desserts[this.editedIndex], this.editedItem)
        } else {
          this.desserts.push(this.editedItem)
        }
        this.close()
      },
    },
  }
</script>
<style>


.mobile {
      color: #333;
    }

    @media screen and (max-width: 768px) {
      .mobile table.v-table tr {
        max-width: 100%;
        position: relative;
        display: block;
      }

      .mobile table.v-table tr:nth-child(odd) {
        border-left: 6px solid deeppink;
      }

      .mobile table.v-table tr:nth-child(even) {
        border-left: 6px solid cyan;
      }

      .mobile table.v-table tr td {
        display: flex;
        width: 100%;
        border-bottom: 1px solid #f5f5f5;
        height: auto;
        padding: 10px;
      }

      .mobile table.v-table tr td ul li:before {
        content: attr(data-label);
        padding-right: .5em;
        text-align: left;
        display: block;
        color: #999;

      }
      .v-datatable__actions__select
      {
        width: 50%;
        margin: 0px;
        justify-content: flex-start;
      }
      .mobile .theme--light.v-table tbody tr:hover:not(.v-datatable__expand-row) {
        background: transparent;
      }

    }
    .flex-content {
      padding: 0;
      margin: 0;
      list-style: none;
      display: flex;
      flex-wrap: wrap;
      width: 100%;
    }

    .flex-item {
      padding: 5px;
      width: 50%;
      height: 40px;
      font-weight: bold;
    }
</style>
