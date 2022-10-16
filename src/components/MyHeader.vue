<template>
    <div className="container">
        <div className="purchase-order">
            <div>
                <h2>Purchase Order</h2>
                <p>{order.header.number}</p>
                <p>SerialMe <span>{order.header.serial}</span></p>
            </div>
        </div>
        <div className="store-name">
            
        </div>
        <div className="value">
            
        </div>
        <div className="suplier">

        </div>
        <div className="ship-to">
            <h2 class="subtitle-footer"></h2>
        </div>
        <div className="bill-to">
            <h2 class="subtitle-footer"></h2>
        </div>
        <div className="charge-to">
            <h2 class="subtitle-footer"></h2>
        </div>
    </div>
</template>

<script>
export default{
    name: 'MyHeader'
}
</script>
