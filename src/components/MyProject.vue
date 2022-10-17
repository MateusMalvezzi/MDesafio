<template v-if="informations === informations">
    <div id="app">
        <div class="container" v-for="information in informations" :key="information.id">
    
            <!--Header -->

            <div class="purchase-order">
                <div class="order">
                    <h2 class="title-purchase">Purchase Order</h2>
                    <p class="number">{{ informations.header.number }}</p>
                    <p class="serial">SerialMe {{informations.header.serial}}</p>
                </div>
            </div>
            <div class="store-name">
                <p class="title">{{ informations.header.buyer }}</p>
                <p class="info-api">{{ informations.header.contact.name }}</p>
                <p class="info-api" style="text-decoration: underline; color: rgb(10, 140, 204);">{{ informations.header.contact.email }}</p>
                <p class="info-api">{{ informations.header.contact.phone }}</p>
                <p class="info-api">{{ informations.header.contact.fax }}</p>
            </div>
            <div class="value">
                <p class="price-currency">{{informations.header.currency}} {{informations.header.price}}</p>
                <p class="status">{{informations.header.status}}</p>
                <p class="create">{{informations.header.createdAt}}</p>
            </div>

            <!-- SUPPLIER -->
            <div class="suplier">
                <div class="suplier-address">
                    <p class="title-suplier">Supplier</p>
                    <p class="subtitle-suplier"><span>{{ informations.supplier.name}}</span><span class="code-suplier">Code #{{informations.supplier.code}}</span></p>
                </div>
                <div class=info-general>
                    <p>{{informations.supplier.document.value}}</p>
                    <p>{{informations.supplier.address}}</p>
                </div>
                <div class="info-contact">
                    <p>{{informations.supplier.contact.name}}</p>
                    <p>{{informations.supplier.contact.email}}</p>
                    <p>{{informations.supplier.contact.phone}}</p>
                    <p>{{informations.supplier.contact.fax}}</p>
                </div>
                <div class="info-read">
                    <p>{{informations.supplier.readAt}}</p>
                    <p>{{informations.supplier.lastReplyAt}}</p>
                </div>
            </div>

            <!-- FOOTER -->
                <div class="ship-to">
                    <h2 class="subtitle-footer">{{ informations.addresses[0].label }}</h2>
                    <h3>{{ informations.addresses[0].name }}</h3>
                    <p class="info-api">{{ informations.addresses[0].address }}</p>
                    <p class="info-api">{{ informations.addresses[0].contact.name }}</p>
                    <p class="info-api">{{ informations.addresses[0].contact.email }}</p>
                    <p class="info-api">{{ informations.addresses[0].contact.phone }} {{ informations.addresses[0].contact.fax }}</p>
                </div>
                <div class="bill-to">
                    <h2 class="subtitle-footer">{{ informations.addresses[1].label }}</h2>
                    <h3>{{ informations.addresses[1].name }}</h3>
                    <p class="info-api">{{ informations.addresses[1].address }}</p>
                    <p class="info-api">{{ informations.addresses[1].contact.name }}</p>
                    <p class="info-api">{{ informations.addresses[1].contact.email }}</p>
                    <p class="info-api">{{ informations.addresses[1].contact.phone }} {{ informations.addresses[1].contact.fax }}</p>
                </div>
                <div class="charge-to">
                    <h2 class="subtitle-footer">{{ informations.addresses[2].label }}</h2>
                    <h3>{{ informations.addresses[2].name }}</h3>
                    <p class="info-api">{{ informations.addresses[2].address }}</p>
                    <p class="info-api">{{ informations.addresses[2].contact.name }}</p>
                    <p class="info-api">{{ informations.addresses[2].contact.email }}</p>
                    <p class="info-api">{{ informations.addresses[2].contact.phone }} {{ informations.addresses[2].contact.fax }}</p>
                </div>
        </div>
    </div>
</template>

<script>
import api from '../services/api'

export default{
    name: 'MyProject',
    data(){
        return{
            informations:null
        }
    },

    mounted () {
      api
        .get('https://me-frontend-challenge-api.herokuapp.com/orders/1')
        .then(response => {
          this.informations = response.data
        })
        .catch(error => console.log(error))
    },
}
</script>
