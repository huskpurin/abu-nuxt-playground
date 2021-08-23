<template>
    <div>
        <p v-for="n in 100" v-bind:key="n">
        {{ n }}
        </p>
        <lazy-component>
            <minor-component />
        </lazy-component>
    </div>
</template>
<script>
export default {
    components: {
        'minor-component': () => import('@/components/test/MinorComponent')
    },
}
</script>
