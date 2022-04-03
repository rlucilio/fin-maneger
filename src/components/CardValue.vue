<template>
    <main class="card-value-info" @click="props.action">
        <Icon :name="props.icon ? props.icon : 'sack-dollar-solid'" class="icon" />
        <div class="content">
            <p class="text highlight">{{ props.value ? formatValue(props.value, props.type) : 0 }}</p>
            <p class="text">{{props.description}}</p>
        </div>
    </main>
</template>

<script lang="ts" setup>
import Icon from "./Icon.vue";

type TypeValue = 'percentage' | 'money';
interface Props {
    type: TypeValue,
    value: number,
    description: string,
    icon: string,
    action?: () => void
}

const props = defineProps<Props>()

function formatValue(value: number, type: TypeValue) {
    if (type === 'money') {
        return new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(value)
    } else {
        return `${new Intl.NumberFormat('pt-BR').format(value)} %`
    }
}

</script>

<style lang="scss" scoped>
.card-value-info {
    display: flex;
    padding: 16px;
    align-items: center;
    width: fit-content;
    min-width: 300px;

    &:hover {
        cursor: pointer;
        background-color: var(--color-background-mute);
    }

    .icon {
        margin-right: 16px;
    }

    .text {
        &.highlight {
            color: var(--color-heading);
            font-size: 1.5rem;
        }
    }
}
</style>