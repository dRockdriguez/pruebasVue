<template>
<div>
    <h2>Tipo de cuenta: {{ cuenta }}</h2>
    <h2 :class="{'active': this.saldo > 0, 'inactive': this.saldo <= 0}">Saldo: {{ saldo }}</h2>
    <h2 :class="{'active': estado, 'inactive': !estado}">{{ estado ? 'La cuenta está activa': 'La cuenta está inactiva' }}</h2>
    <div v-for="(s, i) in servicios" :key="i">
        {{ i + 1 }} - {{ s }}
    </div>
    <accion-saldo text="Añadir saldo"
        @action="addSaldo"/>
    <accion-saldo text="Restar saldo"
        @action="restSaldo"
        :disabled="this.saldo <= 0"/>
</div>
</template>

<script>
import AccionSaldo from './AccionSaldo';

export default {
    components: {
        AccionSaldo
    },
    data() {
        return {
            saldo: 1000,
            cuenta: "Visa",
            estado: true,
            servicios: ['giro', 'abono', 'transferencia']
        }
    },
    methods: {
        addSaldo() {
            this.saldo += 100;
        },
        restSaldo() {
            if(this.saldo <= 0) {
                return;
            }
            this.saldo -= 100;
        }
    }
}
</script>

<style>
    .active {
        color: green;
    }
    .inactive {
        color: red
    }
</style>