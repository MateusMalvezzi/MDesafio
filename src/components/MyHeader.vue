<template>
    <div className="container" 
    v-for="information in informations" :key="information.id">
        <div className="purchase-order">
            <div>
                <h2>Purchase Order</h2>
                <p>{{ informations.header.number }}</p>
                <p>SerialMe <span>{{informations.header.serial}}</span></p>
            </div>
        </div>
        <div className="store-name">
            <p class="title">{{ informations.header.buyer }}</p>
            <p class="info-api">{{ informations.header.contact.name }} info</p>
            <p class="info-api" style="text-decoration: underline; color: #0A8CCC">{{ informations.header.contact.email }}</p>
            <p class="info-api">{{ informations.header.contact.phone }}</p>
            <p class="info-api">{{ informations.header.contact.fax }}</p>
        </div>
        <div className="value">
            <p class="info-api">{{informations.header.currency}} {{informations.header.price}}</p>
            <p class="info-api">{{informations.header.status}}</p>
            <p class="info-api">{{informations.header.createdAt}}</p>
        </div>
        <div className="suplier">
            <p class="title-supplier">Supplier</p>
            <p class="info-api">{{informations.supplier.name}}</p>
            <p class="info-api">{{informations.supplier.code}}</p>
            <p class="info-api">{{informations.supplier.document.value}}</p>
            <p class="info-api">{{informations.supplier.address}}</p>
            <p class="info-api">{{informations.supplier.contact.name}}</p>
            <p class="info-api">{{informations.supplier.contact.email}}</p>
            <p class="info-api">{{informations.supplier.contact.phone}}</p>
            <p class="info-api">{{informations.supplier.contact.fax}}</p>
            <p class="info-api">{{informations.header.readAt}}</p>
            <p class="info-api">{{informations.header.lastReplyAt}}</p>
        </div>
        
        <h2 class="title-footer">Addresses</h2>
        <footer>
            <div className="ship-to">
                <h2 class="subtitle-footer">{{ informations.addresses[0].label }}</h2>
                <h3>{{ informations.addresses[0].name }}</h3>
                <p class="info-api">{{ informations.addresses[0].address }}</p>
                <p class="info-api">{{ informations.addresses[0].contact.name }}</p>
                <p class="info-api">{{ informations.addresses[0].contact.email }}</p>
                <p class="info-api">{{ informations.addresses[0].contact.phone }} {{ informations.addresses[0].contact.fax }}</p>
            </div>
            <div className="bill-to">
                <h2 class="subtitle-footer">{{ informations.addresses[1].label }}</h2>
                <h3>{{ informations.addresses[1].name }}</h3>
                <p class="info-api">{{ informations.addresses[1].address }}</p>
                <p class="info-api">{{ informations.addresses[1].contact.name }}</p>
                <p class="info-api">{{ informations.addresses[1].contact.email }}</p>
                <p class="info-api">{{ informations.addresses[1].contact.phone }} {{ informations.addresses[1].contact.fax }}</p>
            </div>
            <div className="charge-to">
                <h2 class="subtitle-footer">{{ informations.addresses[2].label }}</h2>
                <h3>{{ informations.addresses[2].name }}</h3>
                <p class="info-api">{{ informations.addresses[2].address }}</p>
                <p class="info-api">{{ informations.addresses[2].contact.name }}</p>
                <p class="info-api">{{ informations.addresses[2].contact.email }}</p>
                <p class="info-api">{{ informations.addresses[2].contact.phone }} {{ informations.addresses[2].contact.fax }}</p>
            </div>
        </footer>
    </div>
</template>

<script>
import api from '../services/api'

export default{
    name: 'MyHeader',
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
